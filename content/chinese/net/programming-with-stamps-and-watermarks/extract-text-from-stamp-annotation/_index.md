---
title: 从图章注释中提取文本
linktitle: 从图章注释中提取文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档中的图章注释中轻松提取文本。
type: docs
weight: 80
url: /zh/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 从 PDF 文档中的图章注释中提取文本。我们将向您展示如何使用提供的 C# 源代码从 PDF 文档给定页面上的特定图章注释中提取文本。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "test.pdf");
```

请务必将“您的文档目录”替换为 PDF 文档所在目录的实际路径。

## 步骤 3：从图章注释中提取文本

现在您已经加载了 PDF 文档，您可以从特定图章注释中提取文本。就是这样：

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

上面的代码从 PDF 文档的指定页面检索图章注释，然后使用文本吸收器从注释的外观中提取文本。然后，提取的文本将显示在输出中。

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

恭喜！您已了解如何使用 Aspose.PDF for .NET 从 PDF 文档中的图章注释中提取文本。您现在可以使用此方法从 PDF 文档中的其他注释中提取文本。

### 从图章注释中提取文本的常见问题解答

#### 问：什么是 PDF 文档中的图章注释？为什么需要从中提取文本？

答：PDF 文档中的图章注释是一种图形元素，可用于提供附加信息，例如水印或橡皮图章。当您想要从这些注释中检索基于文本的内容（其中可能包括注释、标签或其他文本信息）时，从图章注释中提取文本非常有用。

#### 问：提供的 C# 源代码如何从图章注释中提取文本？

答：提供的源代码演示了如何从 PDF 文档的给定页面上的特定图章注释中提取文本。它使用 Aspose.PDF 库来检索图章注释，使用`TextAbsorber`，然后在输出中显示提取的文本。

#### 问：我可以使用类似的方法从不同类型的注释中提取文本吗？

答：是的，您可以使用类似的方法从其他类型的注释中提取文本，例如文本注释或弹出注释。您需要修改代码以定位要从中提取文本的特定注释类型。

#### 问：这样做的目的是什么`TextAbsorber` class in the code?

答： 的`TextAbsorber`类用于从 PDF 文档的不同部分提取文本，包括图章注释。它“吸收”或捕获 PDF 指定区域或元素中的文本内容。

#### 问：如何识别要从中提取文本的特定图章注释？

答：在提供的代码中，通过访问标记注释来识别`Annotations`特定页面的集合并使用索引来检索所需的注释。您可以调整索引或使用其他标准来识别目标注释。

#### 问：我可以从同一页面上的多个图章注释中提取文本吗？

 A：是的，你可以修改代码来循环遍历`Annotations`页面的集合，过滤掉图章注释，并从每个页面中提取文本。

#### 问：印章注释没有文字怎么办？代码仍然有效吗？

答：该代码仍然可以工作，但如果图章注释的外观不包含任何文本内容，它将提取并显示一个空字符串。

#### 问：如何将提取的文本保存到文件而不是在输出中显示？

答：您可以修改代码，将提取的文本保存到文件中，而不是将其显示在控制台中。只需更换`Console.WriteLine`带有将文本写入文件的代码的语句。

#### 问：如何使用提取的文本进行进一步处理或分析？

答：使用提供的方法提取文本后，您可以将其存储在变量中，对其进行操作、分析，或根据需要将其集成到应用程序的其他部分。