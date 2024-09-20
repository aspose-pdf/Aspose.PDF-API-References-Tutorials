---
title: 在 PDF 文件中的图像周围放置文本
linktitle: 在 PDF 文件中的图像周围放置文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中的图像周围放置文本。按照我们的分步指南创建并排显示图像和文本的专业 PDF。
type: docs
weight: 260
url: /zh/net/programming-with-text/placing-text-around-image/
---
## 介绍

您是否曾尝试在 PDF 文件中的图像周围放置文本，但发现这很困难？如果是这样，那么您来对地方了！Aspose.PDF for .NET 使这个过程变得简单，允许您仅用几行代码将文本放在图像旁边。无论您是创建报告、文档还是演示文稿，此功能都是增强内容布局并使其更具视觉吸引力的绝佳方式。今天，我们将介绍如何使用 Aspose.PDF for .NET 在 PDF 文档中的图像周围放置文本。

## 先决条件

在我们开始编写代码之前，让我们确保我们已经设置好了一切。以下是您需要的内容：

-  Aspose.PDF for .NET：你可以从以下网址下载[这里](https://releases.aspose.com/pdf/net/).
- Visual Studio：确保您已安装最新版本，以便顺利进行。
- .NET Framework：此示例使用 .NET，因此请确保您的环境已设置为进行 .NET 开发。
- 临时执照：您可以申请临时执照[这里](https://purchase.aspose.com/temporary-license/)如果您正在评估该产品。

如果你尚未设置 Aspose.PDF for .NET，请按照[文档](https://reference.aspose.com/pdf/net/).

## 导入命名空间

在开始编码之前，我们需要导入必要的命名空间。以下是执行此操作的代码片段：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这些命名空间非常重要，因为它们提供了对以下类的访问：`Document`, `Page`, `Image`， 和`HtmlFragment`，我们将使用它来创建和操作 PDF。

现在我们已经做好了准备，让我们来分析一下如何使用 Aspose.PDF for .NET 在 PDF 文件中的图像周围放置文本。我们将逐步指导您完成这一步。

## 步骤 1：实例化文档对象

首先，您需要创建一个 PDF 文档。在 Aspose.PDF 中，这是通过实例化`Document`对象。此对象将作为我们添加的所有内容的基础。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

这里我们创建了一个空的 PDF 文档。它还没有任何页面，但不用担心，我们将在下一步中添加页面。

## 步骤 2：向文档添加页面

现在我们已经有了文档，是时候添加页面了。想象一下创建一张白纸，您可以在其中添加内容。

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

此代码向文档添加了一个新页面。默认情况下，该页面是空白的，但我们即将更改这种情况。

## 步骤 3：创建表格来组织内容

为了使图像和文本保持正确对齐，我们将使用表格。PDF 中的表格可以帮助构建布局，就像在 Word 文档或 HTML 中一样。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

此代码片段创建一个表格并将其添加到页面。将表格视为对齐图像和文本的框架。

## 步骤 4：设置表格的列宽

现在我们已经添加了一个表格，我们需要定义列的宽度。这可以确保图像和文本在页面上的大小合适。

```csharp
table1.ColumnWidths = "120 270";
```

此行设置两列的宽度——一列用于图片，一列用于文本。如果您的图片或文本需要更多或更少的空间，请调整这些值。

## 步骤 5：定义边距和填充

为了确保一切看起来整洁，让我们给表格添加一些边距和填充。

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

这些设置可确保您的表格具有一致的间距，使内容具有视觉吸引力。

## 步骤 6：将图像插入表格

现在，让我们进入最有趣的部分 — 添加图像。在本例中，我们将添加 Aspose 徽标，但您可以随意使用任何您喜欢的图像。

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

以下是具体情况：
- 我们从您指定的目录加载图像。
- 我们设置图像的高度和宽度。
- 最后，我们将图像添加到表格的第一个单元格。

## 步骤 7：在图像旁边添加文本

现在图片已经就位，让我们在图片旁边添加一些文本。在本例中，我们将使用 HTML 格式的文本来设置内容样式。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

此块在图像旁边的单元格中添加了样式化的标题和描述。您可以使用 HTML 标签格式化文本，以实现更多自定义。

## 步骤 8：调整垂直对齐

默认情况下，表格单元格中的内容可能不会按您想要的方式对齐。在这种情况下，我们希望确保文本与单元格顶部对齐。

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

这可确保文本位于单元格的顶部，从而保持布局整洁和专业。

## 步骤 9：在图片和说明下方添加更多文字

您可能希望在图片和文本下方包含更多内容。为此，我们在表格中添加另一行。

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

在这里，我们添加了另一行附加文本，跨越两列以保持布局平衡。

## 步骤 10：保存 PDF 文档

最后，我们需要保存文档，以便您可以查看更改。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

这将保存 PDF，其中的图像和文本格式正是我们想要的。

## 结论

在 PDF 中的图像周围放置文本似乎是一项艰巨的任务，但 Aspose.PDF for .NET 简化了该过程。通过利用表格、图像和样式文本，您可以轻松创建具有专业外观的 PDF。只需几行代码，您就可以将内容准确地放置在您想要的位置，使您的文档具有精致且井井有条的外观。

## 常见问题解答

### 我可以使用此方法放置多张带有文字的图片吗？
是的，只需在表中添加更多行和单元格即可包含更多图像和文本。

### 我可以改变图像的对齐方式吗？
当然可以！您可以通过调整单元格的对齐属性来修改图像对齐。

### 我如何进一步设置文本样式？
您可以在`HtmlFragment`对象应用各种样式，如粗体、斜体或不同的字体。

### 我可以控制文本和图像之间的间距吗？
是的，使用`MarginInfo`对象允许您控制元素之间的填充和边距。

### 是否可以在文本中添加链接？
当然可以！您可以使用`<a>`标签。