# 区域合成示例

这些示例演示了ConditioningSetArea节点的使用。您可以在[ComfyUI](https://github.com/comfyanonymous/ComfyUI)中加载这些图片来获取完整的工作流程。

### 使用Anything-V3进行区域合成 + 使用AbyssOrangeMix2_hard进行第二次处理

这张图片包含4个不同的区域：夜晚、傍晚、白天、早晨

![示例](night_evening_day_morning.png)

这是在ComfyUI中的工作流程展示：

![示例](workflow_night_evening_day_morning.png)

这张图片包含与前一张相同的区域，但顺序相反。

![示例](morning_day_evening_night.png)

通过添加另一个区域提示词，在图片底部中心添加一个主体。

![示例](night_evening_day_morning_subject.png)


## 使用区域合成提高图像一致性

Stable Diffusion在生成接近512x512的正方形图像时，能创建出最一致的图像。但如果我们想要生成一个16:9宽高比的图像呢？
让我们生成一个带有坐姿主体的16:9图像。如果正常生成，成功率会很低，可能会出现四肢不自然地延伸到整个图像，以及其他一致性问题。

通过为主体使用正方形区域的区域合成，一致性会更高，并且由于它是与图像的其余部分同时生成的，整体图像的一致性会非常出色。

这个工作流程使用Anything-V3，这是一个两步工作流程，在第一步中使用区域合成将主体放在图像的左侧。进行第二步处理的原因仅仅是为了提高分辨率，如果您对1280x704的图像尺寸满意，可以跳过第二步。

![示例](square_area_for_subject.png)

在图像右侧添加一个红发主体，使用区域提示词。

第一步输出（1280x704）：

![示例](square_area_for_2_subjects_first_pass.png)

第二步输出（1920x1088）：

![示例](square_area_for_2_subjects.png)

这个第二步输出图像展示了Stable Diffusion的一个行为特征。第二步没有区域提示词。您会注意到主体1的头发是金色带粉色高光，主体2的头发是粉色而不是红色，这与第一步输出中的情况不同。这是因为Stable Diffusion试图使整体图像保持一致，其副作用之一就是将发色融合在一起。

