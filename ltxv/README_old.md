# Lightricks LTX-Video 模型

[LTX-Video](https://huggingface.co/Lightricks/LTX-Video) 是Lightricks开发的高效视频模型。

使用此模型的关键是提供详细描述性的提示。

下载[ltx-video-2b-v0.9.1.safetensors](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltx-video-2b-v0.9.1.safetensors)或旧版[ltx-video-2b-v0.9.safetensors](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltx-video-2b-v0.9.safetensors)文件并放入您的ComfyUI/models/checkpoints文件夹。

如果您尚未下载，可以下载[t5xxl_fp16.safetensors](https://huggingface.co/Comfy-Org/mochi_preview_repackaged/blob/main/split_files/text_encoders/t5xxl_fp16.safetensors)文件并放入您的ComfyUI/models/text_encoders/文件夹。

### 文本转视频

![示例](ltxv_text_to_video.webp)

[Json格式的工作流程](ltxv_text_to_video.json)

您可以下载此webp动画图片并在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载或拖放以获取工作流程。

### 图像转视频

[输入图像](https://commons.wikimedia.org/wiki/File:Havelock_Island,_Mangrove_tree_on_the_beach,_Andaman_Islands.jpg):
<img src="island.jpg" width="256" />

工作流程:

![示例](ltxv_image_to_video.webp)

[Json格式的工作流程](ltxv_image_to_video.json)

您可以下载此webp动画图片并在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载或拖放以获取工作流程。

