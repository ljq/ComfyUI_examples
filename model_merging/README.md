# 模型合并示例

这些工作流程的核心思想是：您可以进行包含多个模型合并的复杂工作流程，测试它们，然后在满意结果时通过取消静音CheckpointSave节点来保存检查点。默认情况下，CheckpointSave节点会将检查点保存到output/checkpoints/文件夹。

您可以在以下位置找到这些节点：advanced->model_merging

第一个示例是两个不同检查点之间简单合并的基础示例。

您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这些图像以获取完整工作流程。

![Example](model_merging_basic.png)

在ComfyUI中，保存的检查点包含用于生成它们的完整工作流程，因此可以像加载图像一样在UI中加载它们以获取创建它们时使用的完整工作流程。

这个示例展示了使用简单块合并来合并3个不同检查点，其中unet的输入、中间和输出块可以有不同的比例：

![Example](model_merging_3_checkpoints.png)

由于Loras是对模型权重的补丁，它们也可以合并到模型中：

![Example](model_merging_lora.png)

您还可以像这个示例中那样减去模型权重并相加，使用公式`(inpaint_model - base_model) * 1.0 + other_model`从非修复模型创建修复模型。
如果您熟悉其他UI中的"Add Difference"选项，这就是在ComfyUI中实现它的方法。

![Example](model_merging_inpaint.png)

需要注意的重要一点是，模型会按照您硬件上用于推理的精度进行合并和保存，因此通常是16位浮点数。如果想以32位浮点数进行合并，请使用以下命令启动ComfyUI：--force-fp32


### 高级合并

#### CosXL

这是一个通过合并从常规SDXL模型创建CosXL模型的示例。需要准备[CosXL基础模型](https://huggingface.co/stabilityai/cosxl)、[SDXL基础模型](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0/blob/main/sd_xl_base_1.0_0.9vae.safetensors)以及您想要转换的SDXL模型。在本示例中我使用了[albedobase-xl](https://civitai.com/models/140737/albedobase-xl)。

![Example](model_merging_cosxl.png)


