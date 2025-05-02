# 3D 示例

## Stable Zero123

Stable Zero123是一个扩散模型，它可以根据一张包含物体和简单背景的图像，生成该物体从不同角度的视图。

[模型权重可以在这里下载](https://huggingface.co/stabilityai/stable-zero123/blob/main/stable_zero123.ckpt) 请将其放入ComfyUI/models/checkpoints文件夹中。

您可以下载此图片并加载它，或将其拖拽到[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中以获取工作流程。

![示例](stable_zero123_example.png)

输入图像可以在[这里](../hypernetworks/hypernetwork_example_output.png)找到，它是[hypernetworks](../hypernetworks)示例的输出图像。

仰角（Elevation）和方位角（Azimuth）以度为单位，用于控制物体的旋转。
