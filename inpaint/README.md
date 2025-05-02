# 图像修复示例

![Example](inpaint_example.png)

在这个示例中我们将使用这张图片。请下载它并放入您的输入文件夹。

![Example](yosemite_inpaint_example.png)

这张图片的部分区域已用GIMP擦除为alpha通道，我们将使用alpha通道作为图像修复的遮罩。如果使用GIMP，请确保保存透明像素的值以获得最佳效果。

ComfyUI还提供了一个遮罩编辑器，可以通过在LoadImage节点中右键点击图片并选择"Open in MaskEditor"来访问。


The following images can be loaded in [ComfyUI](https://github.com/comfyanonymous/ComfyUI) to get the full workflow.

Inpainting a cat with the v2 inpainting model:

![Example](inpain_model_cat.png)

Inpainting a woman with the v2 inpainting model:

![Example](inpain_model_woman.png)

It also works with non inpainting models. Here's an example with the anythingV3 model:

![Example](inpaint_anythingv3_woman.png)

### Outpainting

You can also use similar workflows for outpainting. Outpainting is the same thing as inpainting. There is a "Pad Image for Outpainting" node to automatically pad the image for outpainting while creating the proper mask. In this example this image will be outpainted:

![Example](yosemite_outpaint_example.png)


Using the v2 inpainting model and the "Pad Image for Outpainting" node (load it in ComfyUI to see the workflow):

![Example](inpain_model_outpainting.png)

