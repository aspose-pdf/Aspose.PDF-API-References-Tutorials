---
title: 在 PDF 文件中将文本放置在图像周围
linktitle: 在 PDF 文件中将文本放置在图像周围
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中的图像周围放置文本。
type: docs
weight: 260
url: /zh/net/programming-with-text/placing-text-around-image/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文件中的图像周围放置文本。我们将使用提供的 C# 源代码逐步完成创建表格、添加图像以及在图像周围放置文本的过程。

## 要求

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

首先，您需要设置要保存生成的 PDF 文件的目录路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含您所需目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档和页面

接下来，我们创建一个`Document`对象并使用以下方法向其添加页面`Pages.Add()`方法。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 3 步：创建表

我们使用以下方法创建一个表`Table`类并将其添加到页面的段落集合中。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## 步骤 4：设置表格列宽和边距

我们设置表格的列宽并创建一个`MarginInfo`对象设置边距。

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## 第 5 步：将图像添加到表中

我们创建一个`Image`对象，指定图片文件路径，并设置图片的固定高度和宽度。然后，我们将图像添加到表格单元格的段落集合中。

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## 第 6 步：在图像周围添加文本

我们创建包含 HTML 格式文本的字符串变量并创建`HtmlFragment`目的。然后，我们将 HTML 文本添加到包含图像的表格单元格中。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## 第 7 步：添加附加文本

我们创建另一个`HtmlFragment`包含其他 HTML 格式文本的对象并将其添加到单独的表格单元格中。

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## 步骤 8：保存 PDF 文档

最后，我们将PDF文档保存到指定的输出文件中。

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
//实例化一个表对象
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//将表格添加到所需部分的段落集合中
page.Paragraphs.Add(table1);
//设置表格的列宽
table1.ColumnWidths = "120 270";
//创建 MarginInfo 对象并设置其左、下、右、上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//将默认单元格填充设置为 MarginInfo 对象
table1.DefaultCellPadding = margin;
//在表中创建行，然后在行中创建单元格
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
//创建要添加到图像右侧的文本对象
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
//将包含 HTML 文本的文本段落添加到表格单元格
row1.Cells[1].Paragraphs.Add(TitleText);
//将行内容的垂直对齐方式设置为 Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
//将第二行的行跨度值设置为 2
SecondRow.Cells[0].ColSpan = 2;
//设置第二行垂直对齐方式为Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
//将包含 HTML 文本的文本段落添加到表格单元格
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
//保存 PDF 文件
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中的图像周围放置文本。通过遵循分步指南并执行提供的 C# 代码，您可以创建表格、添加图像以及在 PDF 文档中的图像周围放置文本。

### 常见问题解答

#### 问：“在 PDF 文件中的图像周围放置文本”教程的目的是什么？

答：“在 PDF 文件中的图像周围放置文本”教程演示了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中的图像周围放置文本。本教程提供分步指南和 C# 源代码，帮助您创建表格、添加图像以及在图像周围放置文本。

#### 问：为什么我要在 PDF 文档中的图像周围放置文本？

答：在图像周围放置文本可以增强 PDF 文档的视觉呈现效果，使其更具吸引力和信息量。此技术通常用于文档、小册子、报告和其他您想要以美观的方式组合图像和文本的材料。

#### 问：如何设置文档目录？

A：设置文档目录：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含要保存生成的 PDF 文件的目录路径。

#### 问：如何创建表格并向其中添加图像？

答：本教程将指导您完成使用以下命令创建表的过程：`Table`类并使用以下命令将图像添加到表中`Image`班级。在将图像文件添加到表格单元格之前，您将指定图像文件路径、高度和宽度。

#### 问：如何在图像周围放置文本？

答：要在图像周围放置文本，您将使用以下命令创建 HTML 格式的文本：`HtmlFragment`班级。该文本将包含标题和正文。然后，您将将此 HTML 文本添加到与图像单元格相邻的表格单元格中。

#### 问：我可以自定义文本和图像的外观吗？

答：是的，您可以使用 HTML 标签和属性自定义文本和图像的外观。例如，您可以设置文本的字体大小、颜色、样式和对齐方式。此外，您可以调整图像的大小和尺寸。

#### 问：如何保存PDF文档？

 A：将图像和文本添加到表格后，您可以使用以下命令保存PDF文档：`Save`的方法`Document`班级。提供所需的输出文件路径作为参数`Save`方法。

#### 问：本教程的预期输出是什么？

答：通过遵循教程并执行提供的 C# 代码，您将生成一个 PDF 文档，演示如何在图像周围放置文本。输出文档将包含一个表格，表格周围有图像和文本。

#### 问：我可以使用 JPG 以外的其他图像格式吗？

答：是的，您可以使用 Aspose.PDF 库支持的不同图像格式，例如 PNG、BMP、GIF 等。创建时`Image`对象，指定所需图像格式的文件路径。

#### 问：本教程需要有效的 Aspose 许可证吗？

答：是的，本教程需要有效的 Aspose 许可证才能正常工作。您可以从 Aspose 网站购买完整许可证或获取 30 天的临时许可证。