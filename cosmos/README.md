# Nvidia Cosmos 模型

[Nvidia Cosmos](https://www.nvidia.com/en-us/ai/cosmos/) 是一个"世界模型"系列。ComfyUI 目前特别支持 7B 和 14B 文本到视频扩散模型以及 7B 和 14B 图像到视频扩散模型。

## 需要下载的文件

你首先需要：

#### 文本编码器和 VAE：

[oldt5_xxl_fp8_e4m3fn_scaled.safetensors](https://huggingface.co/comfyanonymous/cosmos_1.0_text_encoder_and_VAE_ComfyUI/tree/main/text_encoders) 放在：ComfyUI/models/text_encoders/

[cosmos_cv8x8x8_1.0.safetensors](https://huggingface.co/comfyanonymous/cosmos_1.0_text_encoder_and_VAE_ComfyUI/blob/main/vae/cosmos_cv8x8x8_1.0.safetensors) 放在：ComfyUI/models/vae/

注意：oldt5_xxl 与 flux 和其他模型中使用的 t5xxl 不同。
oldt5_xxl 是 t5xxl 1.0，而 flux 和其他模型中使用的是 t5xxl 1.1

#### 视频模型

视频模型可以在[这里找到 safetensors 格式](https://huggingface.co/mcmonkey/cosmos-1.0/tree/main)

本页面的工作流使用 [Cosmos-1_0-Diffusion-7B-Text2World.safetensors](https://huggingface.co/mcmonkey/cosmos-1.0/blob/main/Cosmos-1_0-Diffusion-7B-Text2World.safetensors) 和 [Cosmos-1_0-Diffusion-7B-Video2World.safetensors](https://huggingface.co/mcmonkey/cosmos-1.0/blob/main/Cosmos-1_0-Diffusion-7B-Video2World.safetensors)

这些文件放在：ComfyUI/models/diffusion_models

注意：Text2World 和 Video2World 模型都可以生成视频。Text2World 模型从文本提示生成视频，而 Video2World 模型从图像生成视频。

## 工作流示例

本页面包含两个工作流示例：

1. [文本到视频工作流](text_to_video_cosmos_7B.json) - 使用 Text2World 模型从文本生成视频
2. [图像到视频工作流](image_to_video_cosmos_7B.json) - 使用 Video2World 模型从图像生成视频