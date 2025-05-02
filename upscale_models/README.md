# 放大模型示例

这里展示了如何使用ESRGAN等放大模型的示例。将这些模型放在models/upscale_models文件夹中，然后使用UpscaleModelLoader节点加载它们，并使用ImageUpscaleWithModel节点来应用它们。

以下是一个示例：

![示例](esrgan_example.png)

你可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这张图片来获取工作流。

如果你正在寻找可用的放大模型，可以在[OpenModelDB](https://openmodeldb.info/)上找到一些
