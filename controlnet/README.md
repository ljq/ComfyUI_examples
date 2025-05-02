# ControlNet 和 T2I-Adapter 示例

请注意，在这些示例中，原始图像直接传递给 ControlNet/T2I adapter。

每个 ControlNet/T2I adapter 需要传入特定格式的图像，比如深度图、Canny 边缘图等，具体取决于特定模型的要求，这样才能获得好的结果。

ControlNetApply 节点不会自动将普通图像转换为深度图、Canny 边缘图等。你需要单独处理或使用预处理节点来处理你的图像，这些节点可以在这里找到：[这里](https://github.com/Fannovel16/comfy_controlnet_preprocessors)

你可以在这里找到最新的 controlnet 模型文件：[原始版本](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main) 或 [更小的 fp16 safetensors 版本](https://huggingface.co/comfyanonymous/ControlNet-v1-1_fp16_safetensors/tree/main)

对于 SDXL，stability.ai 发布了 Control Loras，你可以在这里找到：[这里 (rank 256)](https://huggingface.co/stabilityai/control-lora/tree/main/control-LoRAs-rank256) 或 [这里 (rank 128)](https://huggingface.co/stabilityai/control-lora/tree/main/control-LoRAs-rank128)。它们的使用方式与常规 ControlNet 模型文件完全相同（放在同一目录中）。

ControlNet 模型文件放在 ComfyUI/models/controlnet 目录中。

### 涂鸦 ControlNet

这是一个如何使用 controlnets 的简单示例，这个示例使用了涂鸦 controlnet 和 AnythingV3 模型。你可以在 [ComfyUI](https://github.com/comfyanonymous/ComfyUI) 中加载这个图像来获取完整的工作流程。

![示例](controlnet_example.png)

这是我在这个工作流程中使用的输入图像：

<img src="input_scribble_example.png" width="256" />

### T2I-Adapter vs ControlNets

T2I-Adapters 比 ControlNets 效率高得多，所以我强烈推荐使用它们。ControlNets 会显著降低生成速度，而 T2I-Adapters 几乎不会对生成速度产生负面影响。

在 ControlNets 中，ControlNet 模型在每次迭代中都会运行一次。而对于 T2I-Adapter，模型只需运行一次。

T2I-Adapters 在 ComfyUI 中的使用方式与 ControlNets 相同：使用 ControlNetLoader 节点。

这是将在此示例中使用的输入图像 [来源](https://commons.wikimedia.org/wiki/File:Stereogram_Tut_Shark_Depthmap.png)：

<img src="shark_depthmap.png" width="512" />

以下是如何使用深度 T2I-Adapter：

![示例](depth_t2i_adapter.png)

以下是如何使用深度 Controlnet。注意，此示例使用 DiffControlNetLoader 节点，因为使用的是 diff control net。Diff controlnets 需要正确加载模型的权重。DiffControlNetLoader 节点也可以用于加载常规 controlnet 模型。当加载常规 controlnet 模型时，它的行为与 ControlNetLoader 节点相同。

![示例](depth_controlnet.png)

你可以在 [ComfyUI](https://github.com/comfyanonymous/ComfyUI) 中加载这些图像来获取完整的工作流程。

### 姿势 ControlNet

这是将在此示例中使用的输入图像：

![示例](pose_worship.png)

这是一个使用 AnythingV3 和 controlnet 进行第一次传递，然后使用 AOM3A3（abyss orange mix 3）及其 VAE 进行第二次传递（不使用 controlnet）的示例。

![示例](2_pass_pose_worship.png)

你可以在 [ComfyUI](https://github.com/comfyanonymous/ComfyUI) 中加载这个图像来获取完整的工作流程。

### 混合 ControlNets

多个 ControlNets 和 T2I-Adapters 可以像这样组合使用，产生有趣的结果：

![示例](mixing_controlnets.png)

你可以在 [ComfyUI](https://github.com/comfyanonymous/ComfyUI) 中加载这个图像来获取完整的工作流程。

输入图像：

<img src="pose_present.png" width="256" /><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><img src="house_scribble.png" width="256" />

