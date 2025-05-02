# SD3示例

## SD3.5

第一步是下载文本编码器文件(如果您还没有从SD3、Flux或其他模型获取): ([clip_l.safetensors](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/blob/main/text_encoders/clip_l.safetensors)、[clip_g.safetensors](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/blob/main/text_encoders/clip_g.safetensors)和t5xxl)，如果它们尚未在您的ComfyUI/models/text_encoders/文件夹中。对于t5xxl，如果您有超过32GB内存，我推荐[t5xxl_fp16.safetensors](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/blob/main/text_encoders/t5xxl_fp16.safetensors)，否则推荐[t5xxl_fp8_e4m3fn_scaled.safetensors](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/blob/main/text_encoders/t5xxl_fp8_e4m3fn_scaled.safetensors)。

SD3.5模型系列包含一个大型8B模型和一个中型2.5B模型。中型模型速度更快、占用内存更少，但对某些概念的理解可能不够复杂。我建议下载两者并实验它们对您提示词的反应。

sd3.5_large.safetensors](https://huggingface.co/stabilityai/stable-diffusion-3.5-large/tree/main)和[sd3.5_medium.safetensors](https://huggingface.co/stabilityai/stable-diffusion-3.5-medium/tree/main)文件(选择您需要的并放入ComfyUI/models/checkpoints/目录)不包含文本编码器/CLIP权重，因此您必须像以下示例中那样单独加载它们：

![Example](sd3.5_text_encoders_example.png)

要使用[sd3.5_large_turbo.safetensors](https://huggingface.co/stabilityai/stable-diffusion-3.5-large-turbo/tree/main)文件(将其放入ComfyUI/models/checkpoints/目录)，您可以使用上述示例并将步数设置为4，cfg设置为1.2。

为方便起见，有一个易于使用的一体化检查点文件[sd3.5_large_fp8_scaled.safetensors](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/blob/main/sd3.5_large_fp8_scaled.safetensors)(将其放入ComfyUI/models/checkpoints/目录)，可以像其他检查点文件一样在默认工作流程中使用。还有一个用于SD3.5中型的版本：[sd3.5_medium_incl_clips_t5xxlfp8scaled.safetensors](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/blob/main/sd3.5_medium_incl_clips_t5xxlfp8scaled.safetensors)

参见此工作流程示例。

![示例](sd3.5_simple_example.png)

提醒一下，您可以保存这些图像文件并将其拖入或加载到ComfyUI中以获取工作流程。

### SD3.5控制网络

Stability已发布一些官方SD3.5控制网络，您可以在[这里](https://huggingface.co/stabilityai/stable-diffusion-3.5-controlnets)找到这些文件(sd3.5_large_controlnet_canny.safetensors、sd3.5_large_controlnet_depth.safetensors、sd3.5_large_controlnet_blur.safetensors)，它们应放入ComfyUI/models/controlnet目录并与SD3.5大型模型一起使用。

参见此工作流程示例，展示了使用canny边缘检测([sd3.5_large_controlnet_canny.safetensors](https://huggingface.co/stabilityai/stable-diffusion-3.5-controlnets/tree/main))控制网络的效果：

![示例](sd3.5_large_canny_controlnet_example.png)


[旧版SD3中型示例](README_old.md)


