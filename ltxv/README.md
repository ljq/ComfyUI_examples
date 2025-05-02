# Lightricks LTX-Video模型

[LTX-Video](https://huggingface.co/Lightricks/LTX-Video)是lightricks开发的一款高效视频模型。

使用此模型的关键是提供详细描述性的提示词。

下载[ltx-video-2b-v0.9.5.safetensors](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltx-video-2b-v0.9.5.safetensors)文件并放入您的ComfyUI/models/checkpoints文件夹。

如果尚未下载，您可以下载[t5xxl_fp16.safetensors](https://huggingface.co/Comfy-Org/mochi_preview_repackaged/blob/main/split_files/text_encoders/t5xxl_fp16.safetensors)文件并放入您的ComfyUI/models/text_encoders/文件夹。

### 图像转视频

输入图像:
<img src="fox.jpg" width="256" />

#### 仅使用起始图像的简单图像转视频工作流程:

![示例](ltxv_image_to_video_simple.0.9.5.webp)

[Json格式的工作流程](ltxv_image_to_video_simple.0.9.5.json)


#### 使用多个引导图像的更复杂图像转视频工作流程:

![示例](ltxv_image_to_video.0.9.5.webp)

[Json格式的工作流程](ltxv_image_to_video.0.9.5.json)

您可以下载此webp动画图像并将其加载或拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)以获取工作流程。

### 文本转视频

![示例](ltxv_text_to_video_0.9.5.webp)

[Json格式的工作流程](ltxv_text_to_video_0.9.5.json)

您可以下载此webp动画图像并将其加载或拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)以获取工作流程。


[旧版ltxv示例](README_old.md)


