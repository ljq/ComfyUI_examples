# HiDream

[HiDream I1](https://github.com/HiDream-ai/HiDream-I1) 是一个先进的图像扩散模型。

## 需要下载的文件

下载文本编码器文件：

* [clip_l_hidream.safetensors](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/text_encoders/clip_l_hidream.safetensors)
* [clip_g_hidream.safetensors](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/text_encoders/clip_g_hidream.safetensors)
* [t5xxl_fp8_e4m3fn_scaled.safetensors](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/text_encoders/t5xxl_fp8_e4m3fn_scaled.safetensors)
* [llama_3.1_8b_instruct_fp8_scaled.safetensors](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/text_encoders/llama_3.1_8b_instruct_fp8_scaled.safetensors)

将这4个文件放入您的ComfyUI/models/text_encoders目录。

您可以在[这里](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/tree/main/split_files/text_encoders)找到所有文件。您可能已经下载了t5xxl。

VAE可以在[这里](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/vae/ae.safetensors)找到，应放入您的ComfyUI/models/vae/文件夹。这是Flux VAE，所以您可能已经有了。

扩散模型可以在这个[文件夹](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/tree/main/split_files/diffusion_models)中找到

## HiDream开发工作流程

下载[hidream_i1_dev_bf16.safetensors](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/diffusion_models/hidream_i1_dev_bf16.safetensors)并放入您的ComfyUI/models/diffusion_models/目录。

然后您可以在ComfyUI中加载或拖放以下图片获取工作流程：

![示例](hidream_dev_example.png)

## HiDream完整工作流程

下载[hidream_i1_full_fp16.safetensors](https://huggingface.co/Comfy-Org/HiDream-I1_ComfyUI/blob/main/split_files/diffusion_models/hidream_i1_full_fp16.safetensors)并放入您的ComfyUI/models/diffusion_models/目录。

然后您可以在ComfyUI中加载或拖放以下图片获取工作流程：

![示例](hidream_full_example.png)

