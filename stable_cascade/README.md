# Stable Cascade 示例

首先下载 [stable_cascade_stage_c.safetensors 和 stable_cascade_stage_b.safetensors 检查点](https://huggingface.co/stabilityai/stable-cascade/tree/main/comfyui_checkpoints) 并放入 ComfyUI/models/checkpoints 文件夹。

Stable cascade 是一个3阶段过程：首先由Stage C扩散模型生成低分辨率潜在图像，然后由Stage B扩散模型放大该潜在图像，最后由Stage A VAE再次放大并转换为像素空间。

注意：您可以下载本页所有图片，然后在ComfyUI中拖放或加载它们以获取嵌入的工作流程。

## 文本转图像

这是一个基本的文本转图像工作流程：

![示例](stable_cascade__text_to_image.png)

## 图像转图像

这是一个通过编码图像并将其传递给Stage C来实现基本图像转图像的示例：

![示例](stable_cascade__image_to_image.png)

## 图像变体

Stable Cascade支持使用CLIP vision的输出创建图像变体。参见以下工作流程示例：

![示例](stable_cascade__image_remixing.png)

参见下一个工作流程了解如何混合多个图像：

![示例](stable_cascade__image_remixing_multiple.png)

您可以在[unCLIP示例页面](../unclip)找到上述工作流程的输入图像。

## ControlNet

您可以从[这里](https://huggingface.co/stabilityai/stable-cascade/tree/main/controlnet)下载stable cascade controlnets。在这些示例中，我在文件名前添加了stable_cascade_前缀，例如：[stable_cascade_canny.safetensors](https://huggingface.co/stabilityai/stable-cascade/blob/main/controlnet/canny.safetensors), [stable_cascade_inpainting.safetensors](https://huggingface.co/stabilityai/stable-cascade/blob/main/controlnet/inpainting.safetensors)

以下是使用Canny Controlnet的示例：

![示例](stable_cascade__canny_controlnet.png)

以下是使用Inpaint Controlnet的示例，示例输入图像可以在[这里](../inpaint/yosemite_inpaint_example.png)找到。提醒您可以在LoadImage节点中右键单击图像并使用遮罩编辑器进行编辑。

![示例](stable_cascade__inpaint_controlnet.png)

