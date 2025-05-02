# unCLIP模型示例

unCLIP模型是SD模型的特殊版本，除了文本提示外，还可以接收图像概念作为输入。图像通过这些模型自带的CLIPVision进行编码，然后在采样时将提取的概念传递给主模型。

基本上，它让你可以在提示中使用图像。

以下是在ComfyUI中的使用方法（你可以将此图拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)来获取工作流）：

![示例](unclip_example.png)

noise_augmentation控制模型将如何紧密地遵循图像概念。值越低，越会遵循概念。

strength控制它对图像的影响程度。

可以像这样使用多个图像：

![示例](unclip_example_multiple.png)

你会注意到它并不是以传统方式混合图像，而是从两者中提取一些概念并创建一个连贯的图像。

输入图像：

<img src="mountains.png" width="256" /><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><img src="sunset.png" width="256" />

你可以在[这里](https://huggingface.co/stabilityai/stable-diffusion-2-1-unclip/tree/main)找到官方的unCLIP检查点

你可以在这里找到我通过一些巧妙的合并从一些现有的768-v检查点制作的unCLIP检查点：[这里（基于WD1.5 beta 2）](https://huggingface.co/comfyanonymous/wd-1.5-beta2_unCLIP/tree/main)和[这里（基于illuminati Diffusion）](https://huggingface.co/comfyanonymous/illuminatiDiffusionV1_v11_unCLIP/tree/main)

### 更高级的工作流

使用unCLIP检查点的一个好方法是在两步工作流的第一步中使用它们，然后在第二步中切换到1.x模型。以下图像就是这样生成的。（你可以将其加载到[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中获取工作流）：

![示例](unclip_2pass.png)
