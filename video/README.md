# 视频示例

## 图像转视频

截至撰写本文时，有两个图像转视频检查点。以下是官方检查点：[生成14帧视频的版本](https://huggingface.co/stabilityai/stable-video-diffusion-img2vid/blob/main/svd.safetensors)和[生成25帧视频的版本](https://huggingface.co/stabilityai/stable-video-diffusion-img2vid-xt/blob/main/svd_xt.safetensors)。将它们放入ComfyUI/models/checkpoints文件夹。


使用图像转视频模型最基本的方法是给它一个初始图像，如下面使用14帧模型的工作流程所示。
您可以下载此webp动画图像并将其加载或拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)以获取工作流程。

![示例](image_to_video.webp)
[Json格式的工作流程](workflow_image_to_video.json)

如果需要确切的输入图像，可以在[unCLIP示例页面](../unclip)找到

您也可以像这个工作流程那样使用它们，该流程使用SDXL生成初始图像，然后传递给25帧模型：

![示例](txt_to_image_to_video.webp)
[Json格式的工作流程](workflow_txt_to_img_to_video.json)

#### 参数说明：

video_frames: 要生成的视频帧数。

motion_bucket_id: 数值越大，视频中的运动越多。

fps: fps越高，视频越流畅。

augmentation level: 添加到初始图像的噪声量，数值越高视频越不像初始图像。增加它以获得更多运动。

VideoLinearCFGGuidance: 此节点略微改善了这些视频模型的采样，它的作用是在不同帧之间线性缩放cfg。在上面的示例中，第一帧将是cfg 1.0(节点中的min_cfg)，中间帧1.75，最后一帧2.5(采样器中设置的cfg)。这样距离初始帧越远的帧会获得逐渐增加的cfg。
