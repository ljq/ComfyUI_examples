# 噪声潜在空间合成示例

您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这些图像以获取完整工作流程。

以下是噪声潜在空间合成的示例。噪声潜在空间合成是指在图像完全去噪之前，当潜在空间仍然含有噪声时将多个潜在空间合成在一起。由于姿势和主体等一般形状在最初的采样步骤中就已经去噪，这使得我们能够将具有特定姿势的主体定位在图像的任何位置，同时保持高度的一致性。

这是一个示例。该示例包含4个合成在一起的图像：1个背景图像和3个主体。
The total steps is 16. The latents are sampled for 4 steps with a different prompt for each. The background is 1920x1088 and the subjects are 384x768 each. After these 4 steps the images are still extremely noisy. The subjects are then composited (pasted) onto the background with some feathering applied. The rest of the sampling steps are then run on this composited image.


这些示例是使用WD1.5 beta 3 illusion模型完成的。

![示例](noisy_latents_3_subjects.png)

改变主体位置后的效果：

![示例](noisy_latents_3_subjects_.png)

您可以看到，从不同噪声潜在图像合成的主题实际上会相互影响，因为我在提示词中添加了"holding hands"。您还会注意到背景的一致性，这显示了这种方法的强大之处。

这项技术有一些限制，例如无法控制主体细节如眼睛颜色等，但在主体位置、姿势和整体颜色方面效果极佳。
