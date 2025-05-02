# SDXL Turbo 示例

SDXL Turbo是一个SDXL模型，可以在单步中生成一致的图像。你可以使用更多步骤来提高质量。使用它的正确方法是使用新的SDTurboScheduler节点，但它也可能与常规调度器一起工作。

这里是[下载官方SDXL turbo检查点](https://huggingface.co/stabilityai/sdxl-turbo/blob/main/sd_xl_turbo_1.0_fp16.safetensors)的链接

这是使用它的工作流：

![示例](sdxlturbo_example.png)

保存这个图像，然后加载它或将其拖到ComfyUI上以获取工作流。然后我建议在界面中启用Extra Options -> Auto Queue。然后按一次"Queue Prompt"并开始编写你的提示。
