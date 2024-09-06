---
title: 删除单词
linktitle: 删除单词
second_title: Aspose.PDF for .NET API 参考
description: 通过这份全面的分步指南，了解如何使用 Aspose.PDF for .NET 删除 PDF 中的单词。增强您的文档编辑技能。
type: docs
weight: 150
url: /zh/net/annotations/strikeoutwords/
---
## 介绍

您是否曾发现自己需要通过删除 PDF 中的特定文本来强调它？无论您是在审阅文档、标记文本，还是仅仅需要突出显示某些部分，删除单词都是一种很有用的工具。在本教程中，我们将探索如何使用 Aspose.PDF for .NET 来实现这一点。本综合指南将引导您完成每个步骤，确保您拥有在 .NET 应用程序中有效实现此功能所需的所有信息。 

## 先决条件

在我们开始编写代码之前，您需要满足一些先决条件才能继续本教程：

1.  Aspose.PDF for .NET 库：确保您已安装 Aspose.PDF for .NET 库。您可以[点击下载](https://releases.aspose.com/pdf/net/).

2. .NET Framework：确保您的计算机上已安装 .NET Framework。本教程针对 .NET 应用程序而设计。

3. 开发环境：您需要一个像 Visual Studio 这样的 IDE 来编写和运行您的代码。

4. PDF 文档：准备好要使用的 PDF 示例文件。我们将从该文档中删除文本。

5. 基本 C# 知识：熟悉 C# 编程对于理解和实施本教程中的步骤是必要的。

## 导入包

在开始编码之前，我们需要在 .NET 项目中导入必要的命名空间。这将使我们能够访问使用 Aspose.PDF 操作 PDF 文件所需的类和方法。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

这些命名空间对于处理 PDF 文档、处理文本以及添加删除线等注释至关重要。

在本节中，我们将把在 PDF 文档中删除单词的过程分解为简单易懂的步骤。每个步骤都会附有详细说明，以确保您了解所有操作的原理。

## 步骤 1：加载 PDF 文档

第一步是加载要编辑的 PDF 文档。您将在该文档中划掉特定的单词或短语。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir`：此变量保存文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`与您的 PDF 文件所在的实际路径。
- `Document` ： 这`Document`类代表一个 PDF 文档。通过将文件路径传递给其构造函数，我们打开 PDF 文件进行处理。

## 步骤 2：创建 TextFragment 吸收器以查找特定文本

接下来，我们将创建一个实例`TextFragmentAbsorber`在 PDF 文档中搜索特定的文本片段。这使我们能够找到想要删除的文本。

```csharp
//创建 TextFragment Absorber 实例来搜索特定的文本片段
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`：此类用于查找和处理 PDF 文档中的特定文本片段。在此示例中，我们搜索单词“Estoque”。将“Estoque”替换为您要在文档中查找的单词或短语。

## 步骤 3：遍历 PDF 文档的各个页面

现在我们有了`TextFragmentAbsorber`，我们需要遍历PDF文档的每一页来找到指定的文本。

```csharp
//遍历 PDF 文档的页面
for (int i = 1; i <= document.Pages.Count; i++)
{
    //获取 PDF 文档的当前页面
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`：此循环遍历 PDF 文档的每一页。
- `document.Pages[i]`：检索当前正在处理的页面。
- `page.Accept(textFragmentAbsorber)` ：此方法应用`TextFragmentAbsorber`到当前页面，搜索指定的文本。

## 步骤 4：收集并处理文本片段

遍历完所有页面后，我们会收集找到的文本片段并准备进一步处理。

```csharp
//创建吸收性文本片段的集合
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`：此集合存储在文档中找到的所有文本片段。我们将在下一步中使用此集合删除文本。

## 步骤 5：遍历文本片段并将其删除

在此步骤中，我们将循环遍历集合中的每个文本片段并对其应用删除线注释。

```csharp
//迭代文本片段的集合
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    //获取 TextFragment 对象的矩形尺寸
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    //实例化 StrikeOut Annotation 实例
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    //设置删除线注释的属性
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    //将注释添加到文本片段页面的注释集合中
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`：此行检索当前文本片段。
- `Aspose.Pdf.Rectangle`：我们计算文本片段的矩形尺寸来确定在何处应用删除线。
- `StrikeOutAnnotation`：此类表示删除线注释。我们用计算出的矩形和当前页面来实例化它。
- `strikeOut.Opacity`：此属性设置删除线的不透明度，使其可见度达到 80％。
- `strikeOut.Color`：我们将删除线的颜色设置为红色。您可以将其更改为您喜欢的任何颜色。
- `textFragment.Page.Annotations.Add(strikeOut)`：这会将删除线注释添加到页面中。

## 步骤6：保存修改后的PDF文档

最后一步是保存应用删除线的修改后的 PDF 文档。

```csharp
//保存更新的 PDF 文档
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`：这将为修改后的文档创建一个新文件名。原始文件保持不变。
- `document.Save(dataDir)`：将带删除线的PDF文档保存到指定位置。

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 删除 PDF 文档中的特定单词。按照本分步指南，您现在可以通过突出显示或删除文本来自定义 PDF 文档，使其更具动态性并满足您的需求。无论您是在注释法律文件、准备报告还是只是标记文本以供审阅，本教程都为您提供了高效完成这些工作的技能。

## 常见问题解答

### 我可以改变删除线的颜色吗？

是的，你可以通过修改`strikeOut.Color`属性。例如，您可以将其设置为`Aspose.Pdf.Color.Blue`蓝色三振出局。

### 可以一次删除多个单词吗？

当然！`TextFragmentAbsorber`可用于搜索文档中的任何单词或短语。您可以通过迭代`TextFragmentCollection`.

### 如果我只想删除特定页面上的文字该怎么办？

您可以修改遍历页面的循环，使其仅包含要修改的页面。例如，`for (int i = 1; i <= 3; i++)`将仅对前三页应用删除线。

### 如何调整删除线的粗细？

您可以通过修改`Border`的财产`StrikeOutAnnotation`。这允许自定义删除线的外观。

### 保存文档后，有没有办法撤消删除线？

一旦文档被保存，删除线将永久保留。如果您需要保留不带删除线的原始文本，请考虑在应用任何修改之前保存原始文档的备份。