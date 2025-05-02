# Mochi视频模型

[Mochi](https://huggingface.co/genmo/mochi-1-preview)是一款先进的视频模型。

您可以在[这里](https://huggingface.co/Comfy-Org/mochi_preview_repackaged/tree/main/split_files)找到以下工作流程所需的所有模型文件

```
diffusion_models/mochi_preview_bf16.safetensors goes in: ComfyUI/models/diffusion_models/
text_encoders/t5xxl_fp16.safetensors goes in: ComfyUI/models/text_encoders/
vae/mochi_vae.safetensors goes in: ComfyUI/models/vae/
```

如果遇到内存问题，可以选择使用fp8文件替代bf16/fp16版本。

![Example](mochi_text_to_video_example.webp)

您可以下载此webp动画图像并将其加载或拖入[ComfyUI](https://github.com/comfyanonymous/ComfyUI)以获取工作流程。


There is also an all in one fp8 checkpoint [here](https://huggingface.co/Comfy-Org/mochi_preview_repackaged/blob/main/all_in_one/mochi_preview_fp8_scaled.safetensors) that contains the fp8 versions of the files in the above workflow packaged in a single checkpoint.

请注意，使用fp8文件的质量会低于16位版本，但速度可能更快，特别是当您的GPU支持fp8运算时。

Here is the workflow to use it:

![Example](mochi_simple_checkpoint.webp)

