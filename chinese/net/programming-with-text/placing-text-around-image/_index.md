---
title: 在图像周围放置文本
linktitle: 在图像周围放置文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中的图像周围放置文本。
type: docs
weight: 260
url: /zh/net/programming-with-text/placing-text-around-image/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中的图像周围放置文本。我们将使用提供的 C# 源代码逐步完成创建表格、添加图像以及在图像周围放置文本的过程。

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