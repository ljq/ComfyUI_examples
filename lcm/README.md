# LCM示例

LCM模型是专为极少数步骤采样设计的特殊模型。

### LCM Lora

LCM loras是可以将常规模型转换为LCM模型的loras。

LCM SDXL lora可以从[这里](https://huggingface.co/latent-consistency/lcm-lora-sdxl/blob/main/pytorch_lora_weights.safetensors)下载

下载后重命名为：lcm_lora_sdxl.safetensors并放入您的ComfyUI/models/loras目录。

然后您可以在ComfyUI中加载此图像以获取展示如何将LCM SDXL lora与SDXL基础模型配合使用的工作流程：

![示例](lcm_basic_example.png)

关键部分包括使用低cfg值、使用"lcm"采样器以及"sgm_uniform"或"simple"调度器。将ModelSamplingDiscrete节点的采样选项设置为lcm会略微改善结果，因此也建议使用但不总是必要。

其他LCM loras可以在各自的模型上以完全相同的方式使用。
