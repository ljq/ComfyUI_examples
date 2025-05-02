# SDXL示例

SDXL基础检查点可以像[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中的常规检查点一样使用。唯一需要注意的是，为了获得最佳性能，分辨率应设置为1024x1024或其他具有相同像素数量但不同宽高比的分辨率。
例如：896x1152或1536x640都是不错的分辨率。

要使用基础模型与精炼器，您可以使用此工作流程。您可以下载此图像并将其加载或拖入ComfyUI以获取它。

![示例](sdxl_simple_example.png)

您也可以像在此工作流程中那样为基础模型和精炼器提供不同的提示词。

![示例](sdxl_refiner_prompt_example.png)


### ReVision技术

ReVision技术与[unCLIP](../unclip)非常相似，但在概念层面上表现不同。您可以向其传递一个或多个图像，它将从图像中提取概念，并将它们作为灵感创建新图像。

首先下载[CLIP-G Vision](https://huggingface.co/comfyanonymous/clip_vision_g/blob/main/clip_vision_g.safetensors)并将其放入您的ComfyUI/models/clip_vision/目录。


这是一个可以拖入或加载到ComfyUI中的工作流程示例。在以下示例中，正向文本提示词被清零，以便最终输出更紧密地跟随输入图像。

![示例](sdxl_revision_zero_positive.png)


如果想使用文本提示词，可以使用此示例：

![示例](sdxl_revision_text_prompts.png)

请注意，可以使用strength选项来增加每个输入图像对最终输出的影响。它还可以通过使用单个unCLIPConditioning或像上述示例那样将多个链接在一起来处理任意数量的图像。

以下是上述工作流程的输入图像(如果需要)：

<img src="../unclip/mountains.png" width="256" /><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><img src="../unclip/sunset.png" width="256" />
