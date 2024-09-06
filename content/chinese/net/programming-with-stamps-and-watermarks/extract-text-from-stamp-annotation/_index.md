---
title: 从图章注释中提取文本
linktitle: 从图章注释中提取文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地从 PDF 文档中的印章注释中提取文本。
type: docs
weight: 80
url: /zh/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 从 PDF 文档中的印章注释中提取文本。我们将向您展示如何使用提供的 C# 源代码从 PDF 文档给定页面上的特定印章注释中提取文本。

## 步骤 1：设置环境

开始之前，请确保您已准备好以下物品：

- 已安装的 .NET 开发环境。
- 已下载并引用适用于 .NET 的 Aspose.PDF 库到您的项目中。

## 步骤 2：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "test.pdf");
```

请务必将“您的文档目录”替换为 PDF 文档所在目录的实际路径。

## 步骤 3：从邮票注释中提取文本

现在您已加载 PDF 文档，您可以从特定的印章注释中提取文本。操作方法如下：

```csharp
//检索缓冲区注释
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

//创建文本吸收器
TextAbsorber ta = new TextAbsorber();

//访问注释的外观
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

//显示提取的文本
Console.WriteLine(ta.Text);
```

上述代码从 PDF 文档的指定页面检索印章注释，然后使用文本吸收器从注释的外观中提取文本。提取的文本随后显示在输出中。

### 使用 Aspose.PDF for .NET 从图章注释中提取文本的示例源代码 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## 结论

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 从 PDF 文档中的印章注释中提取文本。现在，您可以使用此方法从 PDF 文档中的其他注释中提取文本。

### 从邮票注释中提取文本的常见问题解答

#### 问：PDF 文档中的印章注释是什么？为什么我需要从中提取文本？

答：PDF 文档中的图章注释是一种图形元素，可用于提供附加信息，例如水印或橡皮图章。当您想要从这些注释中检索基于文本的内容（包括注释、标签或其他文本信息）时，从图章注释中提取文本非常有用。

#### 问：提供的 C# 源代码如何从印章注释中提取文本？

答：提供的源代码演示了如何从 PDF 文档给定页面上的特定印章注释中提取文本。它使用 Aspose.PDF 库检索印章注释，使用`TextAbsorber`，然后在输出中显示提取的文本。

#### 问：我可以使用类似的方法从不同类型的注释中提取文本吗？

答：是的，您可以使用类似的方法从其他类型的注释中提取文本，例如文本注释或弹出注释。您需要修改代码以针对要从中提取文本的特定注释类型。

#### 问：`TextAbsorber` class in the code?

答：`TextAbsorber`类用于从 PDF 文档的不同部分提取文本，包括图章注释。它“吸收”或捕获在 PDF 的指定区域或元素中找到的文本内容。

#### 问：如何识别我想要从中提取文本的特定印章注释？

答：在提供的代码中，通过访问`Annotations`特定页面的集合，并使用索引来检索所需的注释。您可以调整索引或使用其他条件来识别目标注释。

#### 问：我可以从同一页面上的多个印章注释中提取文本吗？

答：是的，你可以修改代码来循环遍历`Annotations`收集页面，过滤掉邮票注释，并从每个注释中提取文本。

#### 问：如果邮票注释没有文字内容怎么办？代码还能用吗？

答：代码仍然可以工作，但如果印章注释的外观不包含任何文本内容，它将提取并显示一个空字符串。

#### 问：如何将提取的文本保存到文件中而不是将其显示在输出中？

答：您可以修改代码，将提取的文本保存到文件中，而不是将其显示在控制台中。只需将`Console.WriteLine`带有代码的语句将文本写入文件。

#### 问：如何使用提取的文本进行进一步的处理或分析？

答：一旦您使用提供的方法提取文本，您就可以将其存储在变量中，操作它，分析它，或根据需要将其集成到应用程序的其他部分。