# 2 Pass Txt2Img (高分辨率修复) 示例

这些示例演示了如何实现"高分辨率修复"（Hires Fix）功能。

您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这些图片来获取完整的工作流程。

高分辨率修复实际上就是先创建一个低分辨率图像，然后对其进行放大，再通过img2img处理。请注意，在ComfyUI中，txt2img和img2img是同一个节点。通过向采样器节点传递一个空白图像并设置最大去噪，即可实现Txt2Img。

以下是在ComfyUI中使用基本潜空间放大的简单工作流程：

![示例](hiresfix_latent_workflow.png)

## 非潜空间放大

这是一个使用[esrgan放大器](../upscale_models)进行放大的示例。由于ESRGAN在像素空间中运作，图像必须先转换为像素空间，放大后再转回潜空间。

![示例](hiresfix_esrgan_workflow.png)


## 更多示例

这是一个更复杂的两步工作流程示例，该图像首先使用WD1.5 beta 3 illusion模型生成，然后进行潜空间放大，最后使用cardosAnime_v10进行第二次处理：

![示例](latent_upscale_different_prompt_model.png)


