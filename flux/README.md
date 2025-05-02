# Flux 示例

Flux是由[black forest labs](https://blackforestlabs.ai/announcing-black-forest-labs/)开发的一系列扩散模型

如需易于使用的单文件版本，您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中轻松使用，请参见下方：[FP8检查点版本](#simple-to-use-fp8-checkpoint-version)

## 完整版本

### 常规版本需要下载的文件

如果您的ComfyUI/models/text_encoders/目录中还没有t5xxl_fp16.safetensors或clip_l.safetensors，可以在[此链接](https://huggingface.co/comfyanonymous/flux_text_encoders/tree/main)找到。您可以使用t5xxl_fp8_e4m3fn.safetensors来降低内存使用，但如果您的内存超过32GB，推荐使用fp16版本。

VAE可以在[这里](https://huggingface.co/black-forest-labs/FLUX.1-schnell/blob/main/ae.safetensors)找到，应放入您的ComfyUI/models/vae/文件夹。

### 内存不足时的提示：

使用可以在[下方](#simple-to-use-fp8-checkpoint-version)找到的单文件fp8版本。

您可以在"Load Diffusion Model"节点中将weight_dtype设置为fp8，这将使内存使用量减半，但可能会略微降低质量。您也可以下载示例。

### Flux开发版本

您可以在[这里](https://huggingface.co/black-forest-labs/FLUX.1-dev)找到Flux Dev扩散模型权重。将flux1-dev.safetensors文件放入您的ComfyUI/models/diffusion_models/文件夹。

然后您可以在ComfyUI中加载或拖放以下图片获取工作流程：

![示例](flux_dev_example.png)

### Flux Schnell

Flux Schnell是一个蒸馏的4步模型。

您可以在[这里](https://huggingface.co/black-forest-labs/FLUX.1-schnell/blob/main/flux1-schnell.safetensors)找到Flux Schnell扩散模型权重，此文件应放入您的ComfyUI/models/unet/文件夹。

然后您可以在ComfyUI中加载或拖放以下图片获取工作流程：

![示例](flux_schnell_example.png)

## 简单易用的FP8检查点版本

### Flux开发版本

您可以在[这里](https://huggingface.co/Comfy-Org/flux1-dev/blob/main/flux1-dev-fp8.safetensors)找到Flux dev的易用检查点，可以放入您的ComfyUI/models/checkpoints/目录。

此文件可以使用常规的"Load Checkpoint"节点加载。使用时请确保将CFG设置为1.0。

请注意fp8会略微降低质量，因此如果您有资源，推荐使用官方的完整16位版本。

You can then load or drag the following image in ComfyUI to get the workflow:

![Example](flux_dev_checkpoint_example.png)

### Flux Schnell

For Flux schnell you can get the checkpoint [here](https://huggingface.co/Comfy-Org/flux1-schnell/blob/main/flux1-schnell-fp8.safetensors) that you can put in your: ComfyUI/models/checkpoints/ directory.

You can then load or drag the following image in ComfyUI to get the workflow:

![Example](flux_schnell_checkpoint_example.png)

## Flux Extras

The following examples might require that you have some of the regular flux files that you can find links to at the top of this page.

### Fill (Inpainting) model

Download the [flux1-fill-dev.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-Fill-dev) model file and put it in your ComfyUI/models/diffusion_models/ folder.

Here is an example you can drag in ComfyUI for inpainting, a reminder that you can right click images in the "Load Image" node and "Open in MaskEditor".

![Example](flux_fill_inpaint_example.png)

Here is an example for outpainting:

![Example](flux_fill_outpaint_example.png)


### Redux

The Redux model is a model that can be used to prompt flux dev or flux schnell with one or more images.

Download the [sigclip_vision_patch14_384.safetensors](https://huggingface.co/Comfy-Org/sigclip_vision_384/blob/main/sigclip_vision_patch14_384.safetensors) model and put it in your ComfyUI/models/clip_vision folder and download the [flux1-redux-dev.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-Redux-dev) and put it in your ComfyUI/models/style_models folder.

You can then load or drag the following image in ComfyUI to get the workflow:

![Example](flux_redux_model_example.png)

### Canny and Depth

They are published in two versions, full model format: [flux1-canny-dev.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-Canny-dev) and [flux1-depth-dev.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-Depth-dev), put them in your ComfyUI/models/diffusion_models/ folder

Here is an example for the full canny model:

![Example](flux_canny_model_example.png)

They are also published in lora format that can be applied to the flux dev model: [flux1-canny-dev-lora.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-Canny-dev-lora) and [flux1-depth-dev-lora.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-Depth-dev-lora), put them in your ComfyUI/models/loras/ folder

Here is an example for the depth lora.

![Example](flux_depth_lora_example.png)


### Community Flux Controlnets

XLab and InstantX + Shakker Labs have released Controlnets for Flux. You can find the InstantX Canny model file [here](https://huggingface.co/InstantX/FLUX.1-dev-Controlnet-Canny/blob/main/diffusion_pytorch_model.safetensors) (rename to instantx_flux_canny.safetensors for the example below), the Depth controlnet [here](https://huggingface.co/Shakker-Labs/FLUX.1-dev-ControlNet-Depth/blob/main/diffusion_pytorch_model.safetensors) and the Union Controlnet [here](https://huggingface.co/Shakker-Labs/FLUX.1-dev-ControlNet-Union-Pro/blob/main/diffusion_pytorch_model.safetensors). 

The XLab controlnets can be found here [here](https://huggingface.co/XLabs-AI/flux-controlnet-collections).

Put these files under `ComfyUI/models/controlnet` directory.

Try an example Canny Controlnet workflow by dragging in this image into ComfyUI.

![Example](flux_controlnet_example.png)

If you need an example input image for the canny, use [this](girl_in_field.png). Put it under `ComfyUI/input`.
