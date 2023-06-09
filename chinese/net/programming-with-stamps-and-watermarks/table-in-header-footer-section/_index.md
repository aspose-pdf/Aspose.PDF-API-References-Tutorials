---
title: 页眉页脚部分中的表格
linktitle: 页眉页脚部分中的表格
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉/页脚部分添加表格。
type: docs
weight: 170
url: /zh/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉或页脚部分添加表格。提供的 C# 源代码向您展示了如何创建空 PDF 文档、添加页面、配置标题部分、创建表格、向表格添加行和单元格以及最后保存 PDF 文档。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：创建 PDF 文档和页面

第一步是创建一个实例`Document`类并向文档添加页面。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//实例化一个文档对象
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//在 PDF 文档中创建页面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

请务必将“您的文档目录”替换为您要保存 PDF 文档的目录的实际路径。

## 第 3 步：配置标题部分

现在我们将通过创建一个实例来配置 PDF 文档的标题部分`HeaderFooter`班级。就是这样：

```csharp
//为 PDF 文件创建标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//定义页面的标题部分
page. Header = header;

//设置页眉部分的上边距
header. Margin. Top = 20;
```

## 第 4 步：创建表

现在我们将使用`Table`类并将其添加到标题部分的段落集合中。就是这样：

```csharp
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//将表添加到标题部分的段落集合
header.Paragraphs.Add(tab1);

//定义表格列的宽度
tab1.ColumnWidths = "60,300";
```

上面的代码创建了一个包含两列指定宽度的表格。

## 第 5 步：向表中添加行和单元格

现在我们将使用`Row`类和`Cell`班级。就是这样：

```csharp
//在表格中创建一行并添加单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

//合并第一行的第一个单元格
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//在表中创建另一行并添加一个带有图像的单元格
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## 步骤 6：保存 PDF 文档

一旦表格被添加到标题部分，我们就可以保存 PDF 文档。就是这样：

```csharp
//保存 PDF 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

请务必将“您的文档目录”替换为您要保存 PDF 文档的目录的实际路径。

### 使用 Aspose.PDF for .NET 的表页眉页脚部分中的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用空构造函数来实例化 Document 实例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//在pdf文档中创建一个页面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//创建 PDF 文件的页眉部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//为 PDF 文件设置奇怪的标题
page.Header = header;

//设置页眉部分的上边距
header.Margin.Top = 20;

//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在所需部分的段落集合中添加表格
header.Paragraphs.Add(tab1);

//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//设置表格的列宽
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

//将第一行的行跨度值设置为 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row2 = tab1.Rows.Add();

//设置 Row2 的背景颜色
row2.BackgroundColor = Color.White;

//添加保存图像的单元格
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

//将图像宽度设置为 60
img.FixWidth = 60;

//将图像添加到表格单元格
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//将文本的垂直对齐方式设置为居中对齐
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

//保存 Pdf 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉或页脚部分添加表格。您现在可以通过添加表格来自定义您的页眉和页脚，以在您的 PDF 文档中显示更多信息。
