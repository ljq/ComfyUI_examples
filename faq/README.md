# 常见问题解答

## 为什么即使使用相同的种子，我从a1111 UI得到的图像也不同？

在ComfyUI中，噪声是在CPU上生成的。在CPU上生成噪声使ComfyUI具有种子在不同硬件配置下更可重现的优势，但也意味着它们会生成与a1111等在GPU上生成噪声的UI完全不同的噪声。在GPU与CPU上生成噪声不会以任何方式影响性能。

在ComfyUI中，提示强度也更敏感，因为它们没有被标准化。一个简短的例子是当使用

```(masterpiece:1.2) (best:1.3) (quality:1.4) girl```

a1111 UI实际上做的是类似(但对所有token):

```(masterpiece:0.98) (best:1.06) (quality:1.14) (girl:0.81)```

在ComfyUI中，强度不会像这样被平均化，所以它会完全按照您提示的方式使用强度。

还有许多其他差异，但这两个是影响最大的。


## 为什么使用小于1.9GB的某些检查点会得到不连贯的图像？

一些罕见的检查点如ProtoGen_X3.4不包含CLIP权重。ComfyUI中的CLIPLoader节点可用于加载CLIP模型权重，如[这些可用于SD1.5的CLIP L权重](https://huggingface.co/comfyanonymous/flux_text_encoders/blob/main/clip_l.safetensors)。


## "Load LoRA"节点中的strength_model和strength_clip有什么区别？

这些独立的值控制LoRA分别应用于CLIP模型和主MODEL的强度。在大多数UI中，调整LoRA强度只是一个数字，例如将lora强度设置为0.8等同于将strength_model和strength_clip都设置为0.8。

在ComfyUI中可以同时调整两者的原因是LoRA的CLIP和MODEL/UNET部分很可能学习了不同的概念，因此分别调整它们可以获得更好的图像。
