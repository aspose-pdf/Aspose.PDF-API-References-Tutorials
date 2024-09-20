---
title: 指定 PDF 文件中的行距
linktitle: 指定 PDF 文件中的行距
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南学习如何使用 Aspose.PDF for .NET 在 PDF 中指定行距。非常适合寻求精确文本格式的开发人员。
type: docs
weight: 510
url: /zh/net/programming-with-text/specify-line-spacing/
---
## 介绍

您是否曾为控制 PDF 文件中的行距而苦恼？也许您的文本看起来过于拥挤，或者看起来不像您想要的那样精致。在本教程中，我们将介绍如何使用 Aspose.PDF for .NET 轻松指定 PDF 中的行距。我们将使用一个简单的分步指南，带您从空白 PDF 到包含自定义行距的 PDF。如果您需要精确的文本布局（如报告、发票或证书），这是完美的选择。

## 先决条件

在我们进入代码之前，让我们确保您已获得所需的一切：

1. 已安装 Aspose.PDF for .NET。如果没有，请从[Aspose.PDF下载页面](https://releases.aspose.com/pdf/net/).
2. .NET 开发环境（如 Visual Studio）。
3. TrueType 字体文件（`.ttf` )，我们将在示例中使用它。您可以使用任何字体，但在本指南中，我们将使用`HPSimplified.TTF`字型。
4. C# 和 PDF 操作的基本知识。

如果您准备好了，让我们继续导入必要的包。

## 导入包

在您的 C# 项目中，您需要导入 Aspose.PDF 命名空间才能使用 PDF 功能。操作方法如下：

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

这些命名空间允许您创建和操作 PDF 文档，以及使用文本格式和字体选项。

我们将把这个过程分解成几个小步骤，这样你就可以轻松跟进。每个步骤都将重点关注流程中的一个关键部分，从设置 PDF 到指定行距。

## 步骤 1：设置项目并定义文档目录

我们要做的第一件事是定义文件的位置。这有助于程序知道在哪里找到字体以及在哪里保存生成的 PDF。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

在此步骤中，您将替换`"YOUR DOCUMENT DIRECTORY"`替换为您存储文件的实际路径。这将是您放置字体文件的位置（`HPSimplified.TTF`) 以及 PDF 的保存位置。

## 第 2 步：加载 PDF 文档

现在，我们需要创建一个新的 PDF 文档。在本指南中，我们将从一个空白文档开始，但您也可以根据需要加载现有 PDF。

```csharp
Document doc = new Document();
```

这将创建一个新的空白 PDF 文档。很简单，对吧？

## 步骤 3：设置文本格式选项

这就是奇迹发生的地方。我们将为要添加到 PDF 的文本指定行距模式。Aspose.PDF 为我们提供了几个选项，但在本指南中，我们将使用`LineSpacingMode.FullSize`，以确保完全遵守行距。

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

此代码将行距模式设置为`FullSize`，确保文本以适当的间距显示。还有其他选项，例如`Proportional`如果你想要不同的间距行为，但现在，我们先坚持`FullSize`.

## 步骤 4：创建文本片段

现在，我们将创建将放置在 PDF 中的实际文本。此文本将遵循我们定义的行距。

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

我们用字符串创建了一个文本片段`"Hello world"`。当然，您可以根据自己的喜好自定义此文本。

## 步骤 5：加载并应用自定义字体

为了让文本更加突出，我们将从文件中加载自定义 TrueType 字体。此步骤是可选的，但它可以为您的 PDF 增添专业感。

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

在这里，我们加载字体文件并将其应用于文本片段。如果文件路径有效，则使用该字体。否则，将应用默认字体。

## 步骤 6：设置文本位置和格式

接下来，我们需要在 PDF 上定位文本。我们还将应用之前创建的格式选项。

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

这`Position`方法设置文本在页面上的坐标（在本例中，距左侧 100 个单位，距底部 600 个单位）。此处应用了格式选项，包括行距模式。

## 步骤 7：向 PDF 页面添加文本

现在我们的文本已经格式化并定位，是时候将其添加到 PDF 文档了。

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

此代码在 PDF 文档中创建一个新页面并向其中添加文本片段。

## 步骤 8：保存 PDF

我们已经到了最后一步！现在一切都设置好了，让我们保存 PDF。

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

这将保存具有指定行距的 PDF，并且您的文件已准备好！

## 结论

就这样！您刚刚使用 Aspose.PDF for .NET 创建了一个具有自定义行距的 PDF 文档。这是一个功能强大的工具，可让您控制 PDF 文件的各个方面，这只是您可以实现的功能的一个示例。从文本放置到格式设置，可能性无穷无尽。

如果您想深入了解 PDF 操作，Aspose.PDF 提供了丰富的功能供您探索。不要犹豫，尝试并突破您对文档所能做的极限！

## 常见问题解答

### 我可以将行距调整为其他模式吗？  
是的，你可以使用其他模式，例如`Proportional`或者`Fixed`根据您的需要。

### 是否可以从系统而不是文件加载字体？  
是的，你可以使用`FontRepository`.

### 我可以将 Aspose.PDF for .NET 与其他文件格式一起使用吗？  
当然！Aspose.PDF for .NET支持多种格式，如XML，HTML等。

### 我需要许可证才能使用 Aspose.PDF for .NET 吗？  
是的，要获得完整功能，您需要许可证，您可以获取[这里](https://purchase.aspose.com/buy).

### 如何设置多个段落的行距？  
您可以申请`TextFormattingOptions`对每一个`TextFragment`或者`TextParagraph`控制多行或段落的间距。