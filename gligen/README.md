# GLIGEN示例

这里是[支持的GLIGEN模型文件精简版下载链接](https://huggingface.co/comfyanonymous/GLIGEN_pruned_safetensors/tree/main)

将GLIGEN模型文件放入ComfyUI/models/gligen目录。

### 文本框GLIGEN

文本框GLIGEN模型允许您指定图像中多个对象的位置和大小。要正确使用它，您应该正常编写提示词，然后使用GLIGEN Textbox Apply节点来指定提示词中某些对象/概念在图像中的位置。

![示例](gligen_textbox_example.png)

这是一个使用示例。您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载此图像以获取工作流程。

