# 混元视频模型

[混元视频](https://huggingface.co/tencent/HunyuanVideo)是一个文本转视频模型。


从[这里](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged/tree/main/split_files/text_encoders)下载clip_l.safetensors和llava_llama3_fp8_scaled.safetensors文件，并将它们放入您的ComfyUI/models/text_encoders目录。

下载[hunyuan_video_vae_bf16.safetensors](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged/tree/main/split_files/vae)文件并将其放入您的ComfyUI/models/vae文件夹。

### 文本转视频

下载[hunyuan_video_t2v_720p_bf16.safetensors](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged/tree/main/split_files/diffusion_models)文件并将其放入您的ComfyUI/models/diffusion_models文件夹。

该模型也可以通过将视频长度设置为1来生成静态图像。

![示例](hunyuan_video_text_to_video.webp)

[Json格式的工作流程](hunyuan_video_text_to_video.json)

You can download this webp animated image and load it or drag it on [ComfyUI](https://github.com/comfyanonymous/ComfyUI) to get the workflow.

### 图像转视频

下载[llava_llama3_vision.safetensors](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged/blob/main/split_files/clip_vision/llava_llama3_vision.safetensors)文件并将其放入您的ComfyUI/models/clip_vision/文件夹。

有两种不同的模型可供选择，它们会产生不同的结果。

#### v1 "连接"

第一个模型对引导图像的跟随程度不如另一个模型，但可能会产生更好的运动效果。

下载[hunyuan_video_image_to_video_720p_bf16.safetensors](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged/tree/main/split_files/diffusion_models)文件并将其放入您的ComfyUI/models/diffusion_models/文件夹。

![Example](hunyuan_video_image_to_video.webp)

[Workflow in Json format](hunyuan_video_image_to_video.json)

您可以下载此webp动画图像并将其加载或拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)以获取工作流程。输入图像可以在[flux](../flux)页面找到。

#### v2 "替换"

第二个模型非常紧密地跟随引导图像，但似乎比第一个模型的动态性稍差。

下载[hunyuan_video_v2_replace_image_to_video_720p_bf16.safetensors](https://huggingface.co/Comfy-Org/HunyuanVideo_repackaged/tree/main/split_files/diffusion_models)文件并将其放入您的ComfyUI/models/diffusion_models/文件夹。

![Example](hunyuan_video_image_to_video_v2.webp)

[Workflow in Json format](hunyuan_video_image_to_video_v2.json)

您可以下载此webp动画图像并将其加载或拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)以获取工作流程。输入图像可以在[flux](../flux)页面找到。
