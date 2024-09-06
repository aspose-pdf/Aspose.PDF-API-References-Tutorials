---
title: 在 PDF 文件中的图像周围放置文本
linktitle: 在 PDF 文件中的图像周围放置文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中的图像周围放置文本。
type: docs
weight: 260
url: /zh/net/programming-with-text/placing-text-around-image/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文件中的图像周围放置文本。我们将逐步介绍如何使用提供的 C# 源代码创建表格、添加图像以及在图像周围定位文本的过程。

## 要求

开始之前，请确保您已准备好以下物品：

- 已安装 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 步骤 1：设置文档目录

首先，您需要设置要保存生成的 PDF 文件的目录路径。替换`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量为您所需目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建文档和页面

接下来我们创建一个`Document`对象并使用`Pages.Add()`方法。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 步骤 3：创建表

我们使用`Table`类并将其添加到页面的段落集合中。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## 步骤 4：设置表格列宽和边距

我们设置表格的列宽并创建`MarginInfo`对象来设置边距。

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## 步骤 5：向表中添加图像

我们创建了一个`Image`对象，指定图片文件路径，设置图片的固定高度和宽度，然后我们将图片添加到表格单元格的段落集合中。

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## 步骤 6：在图片周围添加文字

我们创建包含 HTML 格式文本的字符串变量，并创建一个`HtmlFragment`对象。然后，我们将 HTML 文本添加到包含图像的表格单元格中。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## 步骤 7：添加其他文本

我们创造另一个`HtmlFragment`包含附加 HTML 格式文本的对象并将其添加到单独的表格单元格中。

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## 步骤 8：保存 PDF 文档

最后，我们将PDF文档保存到指定的输出文件。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### 使用 Aspose.PDF for .NET 在图像周围放置文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//在 Pdf 中创建页面
Aspose.Pdf.Page page = doc.Pages.Add();
//实例化表对象
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//在所需部分的段落集合中添加表格
page.Paragraphs.Add(table1);
//设置表格的列宽
table1.ColumnWidths = "120 270";
//创建 MarginInfo 对象并设置其左边距、下边距、右边距和上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//将默认单元格填充设置为 MarginInfo 对象
table1.DefaultCellPadding = margin;
//在表格中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = table1.Rows.Add();
//创建图像对象
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
//指定图像文件路径
logo.File = dataDir + "aspose-logo.jpg";
//指定图像固定高度
logo.FixHeight = 120;
//指定图像固定宽度
logo.FixWidth = 110;
row1.Cells.Add();
//将图像添加到表格单元格的段落集合中
row1.Cells[0].Paragraphs.Add(logo);
//使用包含 html 标签的文本创建字符串变量
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//创建一个文本对象添加到图像的右侧
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
//将包含 HTML 文本的文本段落添加到表格单元格
row1.Cells[1].Paragraphs.Add(TitleText);
//将行内容的垂直对齐方式设置为顶部
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//在表格中创建行，然后在行中创建单元格
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
//将第二行的行跨度值设置为 2
SecondRow.Cells[0].ColSpan = 2;
//将第二行的垂直对齐方式设置为“顶部”
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
//将包含 HTML 文本的文本段落添加到表格单元格
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
//保存 Pdf 文件
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中的图像周围放置文本。通过遵循分步指南并执行提供的 C# 代码，您可以创建表格、添加图像并在 PDF 文档中的图像周围放置文本。

### 常见问题解答

#### 问： “在 PDF 文件中的图像周围放置文本”教程的目的是什么？

答：“在 PDF 文件中的图像周围放置文本”教程演示了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中的图像周围放置文本。本教程提供了分步指南和 C# 源代码，以帮助您创建表格、添加图像并在图像周围放置文本。

#### 问：为什么我要在 PDF 文档中的图像周围放置文本？

答：在图片周围放置文字可增强 PDF 文档的视觉效果，使其更具吸引力和信息量。此技术通常用于文档、小册子、报告和其他需要以美观的方式结合图像和文本的材料。

#### 问：如何设置文档目录？

A：设置文档目录：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量为您想要保存生成的 PDF 文件的目录的路径。

#### 问：如何创建表格并向其中添加图像？

答：本教程将指导您使用`Table`类并使用`Image`类。在将图像文件添加到表格单元格之前，您将指定图像文件的路径、高度和宽度。

#### 问：如何在图像周围定位文字？

答：要在图像周围放置文本，您将使用`HtmlFragment`类。此文本将包含标题和正文。然后，您将此 HTML 文本添加到与图像单元格相邻的表格单元格中。

#### 问：我可以自定义文本和图像的外观吗？

答：是的，您可以使用 HTML 标签和属性自定义文本和图片的外观。例如，您可以设置文本的字体大小、颜色、样式和对齐方式。此外，您还可以调整图片的大小和尺寸。

#### 问：如何保存 PDF 文档？

答：将图片和文本添加到表格后，您可以使用`Save`方法`Document`类。将所需的输出文件路径作为参数提供给`Save`方法。

#### 问：本教程的预期输出是什么？

答：按照本教程并执行提供的 C# 代码，您将生成一个 PDF 文档，该文档演示了如何在图像周围放置文本。输出文档将包含一个表格，表格周围放置有图像和文本。

#### 问：我可以使用 JPG 以外的其他图像格式吗？

答：是的，您可以使用 Aspose.PDF 库支持的不同图像格式，例如 PNG、BMP、GIF 等。创建`Image`对象，指定所需图像格式的文件路径。

#### 问：本教程是否需要有效的 Aspose 许可证？

答：是的，本教程需要有效的 Aspose 许可证才能正常运行。您可以从 Aspose 网站购买完整许可证或获取 30 天的临时许可证。