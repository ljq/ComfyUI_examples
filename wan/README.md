Wan 2.1 模型

[Wan 2.1](https://github.com/Wan-Video/Wan2.1) 是一个视频模型系列。

## 需要下载的文件

首先需要下载以下文件：

#### 文本编码器和VAE：

[umt5_xxl_fp8_e4m3fn_scaled.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/tree/main/split_files/text_encoders) 放入: ComfyUI/models/text_encoders/

[wan_2.1_vae.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/vae/wan_2.1_vae.safetensors) 放入: ComfyUI/models/vae/


#### 视频模型

扩散模型可以在[这里](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/tree/main/split_files/diffusion_models)找到

注意：推荐使用fp16版本而非bf16版本，因为它们能提供更好的结果。

质量排序(从高到低): fp16 > bf16 > fp8_scaled > fp8_e4m3fn

这些文件放入: ComfyUI/models/diffusion_models/

这些示例使用16位文件，但如果内存不足可以使用fp8版本。

## 工作流程

### 文本转视频

此工作流程需要[wan2.1_t2v_1.3B_fp16.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_t2v_1.3B_fp16.safetensors)文件(放入: ComfyUI/models/diffusion_models/)。也可以使用14B模型。

![示例](text_to_video_wan.webp)

[Json格式的工作流程](text_to_video_wan.json)

### 图像转视频

此工作流程需要[wan2.1_i2v_480p_14B_fp16.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_i2v_480p_14B_fp16.safetensors)文件(放入: ComfyUI/models/diffusion_models/)和
[clip_vision_h.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/clip_vision/clip_vision_h.safetensors)(放入: ComfyUI/models/clip_vision/)

注意此示例仅生成512x512分辨率的33帧，目的是使其易于运行，实际上模型能处理更多。如果有足够的硬件/耐心，720p模型效果相当不错。

<img src="image_to_video_wan_example.webp" width="512" />

[Json格式的工作流程](image_to_video_wan_example.json)

输入图像可以在[flux](../flux)页面找到。

这是使用[720p](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_i2v_720p_14B_fp16.safetensors)模型的相同示例：

<img src="image_to_video_wan_720p_example.webp" width="768" />
