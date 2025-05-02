# 图像到图像示例

这些示例展示了如何进行图像到图像转换。

您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这些图像以获取完整的工作流程。

图像到图像的工作原理是加载一个图像，如这个[示例图像](https://github.com/comfyanonymous/ComfyUI/blob/master/input/example.png)，使用VAE将其转换为潜在空间，然后使用低于1.0的去噪值进行采样。去噪值控制添加到图像中的噪声量。去噪值越低，添加的噪声越少，图像变化越小。

输入图像应放入input文件夹。

这是一个简单的图像到图像工作流程，它与默认的文本到图像工作流程相同，但去噪值设置为0.87，并且将加载的图像传递给采样器而不是空图像。

![示例](img2img_workflow.png)
