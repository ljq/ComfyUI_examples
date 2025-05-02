# 文本反转嵌入示例

这里展示了如何使用文本反转/嵌入（Textual Inversion/Embeddings）的示例。

![示例](embedding_example.png)

要使用嵌入，请将文件放在models/embeddings文件夹中，然后在提示中使用它，就像我在上图中使用SDA768.pt嵌入那样。

注意，你可以省略文件扩展名，所以以下两种写法是等效的：

```embedding:SDA768.pt```

```embedding:SDA768```


你也可以像调整提示中的普通词语一样设置嵌入的强度：

```(embedding:SDA768:1.2)```


嵌入本质上是自定义词语，所以它们在文本提示中的位置很重要。

例如，如果你有一个猫的嵌入：

```red embedding:cat```

这很可能会给你一只红色的猫。

