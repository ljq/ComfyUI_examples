# Lora 示例

这些示例展示了如何使用Loras。所有LoRA变体：Lycoris、loha、lokr、locon等都这样使用。

您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这些图片获取完整工作流程。

Loras是应用于主MODEL和CLIP模型的补丁，因此要使用它们，请将它们放入models/loras目录并使用LoraLoader节点，如下所示：

![示例](lora.png)

您可以通过链接多个LoraLoader节点来应用多个Loras，如下所示：

![示例](lora_multiple.png)
