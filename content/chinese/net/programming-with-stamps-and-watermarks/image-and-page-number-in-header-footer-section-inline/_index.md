---
title: 页眉页脚部分内联中的图像和页码
linktitle: 页眉页脚部分内联中的图像和页码
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南了解如何使用 Aspose.PDF for .NET 在 PDF 的标题部分内联添加图像和页码。
type: docs
weight: 120
url: /zh/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## 介绍

Aspose.PDF for .NET 是一款功能强大的工具，可提供处理和生成 PDF 文件的广泛功能。无论您需要添加图像、自定义页眉和页脚还是管理文本，Aspose.PDF 都能满足您的需求。在本教程中，我们将探讨如何在 PDF 文档的页眉或页脚中添加内联图像和页码。让我们深入研究并逐步分解该过程。

## 先决条件

在我们进入代码之前，让我们确保您已准备好一切：

-  Aspose.PDF for .NET: 从下载最新版本[Aspose PDF 下载页面](https://releases.aspose.com/pdf/net/).
- 开发环境：您需要一个 C# IDE，例如 Visual Studio。
- 执照：如果你还没有执照，你可以申请[此处为临时执照](https://purchase.aspose.com/temporary-license/)或者从[Aspose 商店](https://purchase.aspose.com/buy).

现在您已经准备好了先决条件，让我们开始吧。

## 导入包

在开始编码之前，请确保导入必要的命名空间：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这些软件包允许您处理 PDF 文件和文本操作。

## 步骤 1：设置文档目录

我们要做的第一件事是定义保存 PDF 文件的目录路径。此路径可以自定义为您的项目文件夹或计算机上的任何位置。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

此变量保存文档的存储位置。替换`"YOUR DOCUMENT DIRECTORY"`与实际路径。

## 步骤 2：实例化 PDF 文档

在此步骤中，我们创建一个新的实例`Aspose.Pdf.Document`对象。此对象将作为 PDF 文件的骨干。

```csharp
//通过调用空构造函数来实例化 Document 对象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

在这里，我们创建一个空白的 PDF 文件，稍后我们可以在其中填充内容。

## 步骤 3：向 PDF 添加页面

您的 PDF 至少需要一页，您可以在其中添加页眉、页脚和内容。让我们在文档中添加一个空白页。

```csharp
//在 Pdf 对象中创建一个页面
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

通过致电`pdf1.Pages.Add()`，新的页面将添加到文档中，可供自定义页眉和页脚。

## 步骤 4：创建并设置标题

现在是时候创建文档的页眉了。我们将在这里添加文本、图像和页码。

```csharp
//创建文档的页眉部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
//设置 PDF 文件的页眉
page.Header = header;
```

我们创建`HeaderFooter`对象并将其分配给`Header`页面的属性，确保我们添加到页眉的任何内容都会出现在页面的顶部。

## 步骤 5：向标题添加内联文本

添加文本就像创建`TextFragment`并指定其属性。让我们在标题中添加一些彩色文本。

```csharp
//创建文本对象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
//指定颜色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

在此步骤中，我们创建一个`TextFragment`内容为“Aspose.Pdf is a Robust component by”，并将其颜色设置为蓝色。`IsInLineParagraph`属性确保文本是内联的，这意味着它将与其他元素（如图像和附加文本）出现在同一行上。

## 步骤 6：在页眉中插入内联图像

为了让标题更具视觉吸引力，您可以添加内嵌于文本的图片。这可以是您的公司徽标或任何其他图形。

```csharp
//在部分中创建一个图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
//设置图片文件路径
image1.File = dataDir + "aspose-logo.jpg";
//设置图片宽度信息
image1.FixWidth = 50;
image1.FixHeight = 20;
//表明 seg1 的 InlineParagraph 是一张图片。
image1.IsInLineParagraph = true;
```

在这里，我们通过创建`Image`对象，设置其路径，并调整宽度和高度。`IsInLineParagraph`确保图像与文本对齐。

## 步骤 7：添加其他内联文本以完成标题

让我们添加一些文本来完成内联标题。

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

在这一部分中，我们创建另一个`TextFragment`内容为“Pty Ltd.”并将其颜色设置为栗色。文本片段和图像均添加到标题中。

## 步骤 8：保存 PDF

设置完页眉后，就可以保存 PDF 了。

```csharp
//保存 PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

这`Save`方法将最终的PDF文件写入指定位置。

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 将图像和文本添加到 PDF 文档的页眉。本教程将引导您完成基本步骤，包括创建文档、添加页面、插入页眉以及放置文本和图像等内联内容。Aspose.PDF 为您提供了管理 PDF 的极大灵活性，无论是操作页眉、页脚还是复杂内容。 

## 常见问题解答

### 我可以在页眉中添加页码吗？
是的！您可以使用`TextFragment`类并根据需要对其进行格式化。只需将其作为内联内容插入到标题部分即可。

### 如何在标题中设置背景图像？
您可以使用`BackgroundImage`的财产`HeaderFooter`类来设置背景图像。但是，这不是内联内容，它将覆盖整个标题区域。

### 除了 JPEG 之外，还可以使用其他图像格式吗？
当然！Aspose.PDF 支持各种图像格式，例如 PNG、BMP 和 GIF。

### 我可以自定义页眉文本的字体吗？
是的，您可以使用`TextState`对象来改变文本的字体、大小和样式。

### 我需要许可证才能使用 Aspose.PDF for .NET 吗？
是的，Aspose.PDF 需要许可证才能使用，但你可以先[点击此处免费试用](https://releases.aspose.com/).