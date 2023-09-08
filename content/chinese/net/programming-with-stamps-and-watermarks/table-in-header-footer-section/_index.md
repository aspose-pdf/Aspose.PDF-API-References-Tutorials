---
title: 页眉页脚部分中的表格
linktitle: 页眉页脚部分中的表格
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉/页脚部分添加表格。
type: docs
weight: 170
url: /zh/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉或页脚部分添加表格。提供的 C# 源代码向您展示了如何创建空 PDF 文档、添加页面、配置标题部分、创建表格、向表格添加行和单元格，最后保存 PDF 文档。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

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

## 步骤 3：配置标头部分

现在我们将通过创建一个实例来配置 PDF 文档的标题部分`HeaderFooter`班级。就是这样：

```csharp
//为 PDF 文件创建标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//定义页面的标题部分
page. Header = header;

//设置标题部分的上边距
header. Margin. Top = 20;
```

## 第四步：创建表

现在我们将使用以下命令创建一个表`Table`类并将其添加到标题部分的段落集合中。就是这样：

```csharp
//实例化一个Table对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//将表格添加到标题部分的段落集合中
header.Paragraphs.Add(tab1);

//定义表格列的宽度
tab1.ColumnWidths = "60,300";
```

上面的代码创建了一个具有两列指定宽度的表格。

## 步骤 5：向表格添加行和单元格

现在我们将使用以下命令将行和单元格添加到表格中`Row`类和`Cell`班级。就是这样：

```csharp
//在表格中创建一行并添加单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

//合并第一行的第一个单元格
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//在表格中创建另一行并添加带有图像的单元格
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

## 第6步：保存PDF文档

将表格添加到标题部分后，我们就可以保存 PDF 文档。就是这样：

```csharp
//保存 PDF 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

请务必将“您的文档目录”替换为您要保存 PDF 文档的目录的实际路径。

### 使用 Aspose.PDF for .NET 的页眉页脚部分中的表的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用空构造函数实例化 Document 实例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//在 pdf 文档中创建页面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//创建 PDF 文件的标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置 PDF 文件的奇数页眉
page.Header = header;

//设置标题部分的上边距
header.Margin.Top = 20;

//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//将表格添加到所需部分的段落集合中
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

//设置文本的垂直对齐方式为居中对齐
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

//保存 PDF 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## 结论

恭喜！您已经了解了如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉或页脚部分添加表格。现在，您可以通过添加表格来自定义页眉和页脚，以在 PDF 文档中显示其他信息。

### 页眉页脚部分表格的常见问题解答

#### 问：在 PDF 文档的页眉或页脚部分添加表格的目的是什么？

答：在 PDF 文档的页眉或页脚部分添加表格可让您显示结构化且有组织的信息，例如标题、副标题、徽标或您希望在文档的每一页上一致显示的任何其他内容。

#### 问：提供的C#源代码如何实现在PDF文档的页眉或页脚部分添加表格？

答：该代码演示了创建空 PDF 文档、添加页面、配置标题部分、创建包含行和单元格的表格以及最后保存 PDF 文档的过程。结果是在 PDF 文档的标题部分显示一个表格。

#### 问：我可以自定义表格单元格的外观，例如边框、背景颜色和文本样式吗？

答：是的，您可以通过设置单元格边框、背景颜色、文本样式、字体、字体大小等属性来自定义表格单元格的外观。

#### 问：如何将表格添加到 PDF 文档的页眉部分？

A：代码将表格添加到页眉部分的段落集合中，这样可以确保表格显示在每个页面的页眉中。

#### 问：我可以根据需要向表格添加更多行和单元格吗？

答：当然，您可以使用以下命令向表格添加更多行和单元格`Rows.Add()`和`Cells.Add()`方法。这允许您根据需要构建表格内容。

#### 问：可以调整表格列的宽度吗？
答：是的，您可以使用`ColumnWidths`财产。这使您能够控制表的布局。

#### 问：如何将单元格跨越表格中的多列或多行？
答：要将单元格跨多列，您可以使用`ColSpan`相应单元格的属性。同样，您可以使用`RowSpan`属性将单元格跨多行。

#### 问：如果我想向 PDF 文档的页眉和页脚部分添加表格，会发生什么情况？

答：您可以对页眉和页脚部分采用类似的方法。只需创建一个`HeaderFooter`页脚的实例，配置它，并将表格添加到其段落集合中。

#### 问：我可以在表格单元格内使用图像吗？如何实现？

答：是的，您可以在表格单元格中添加图像。该代码示例演示了通过创建一个`Image`对象，设置其文件路径和尺寸，然后将其添加到单元格的段落中。

#### 问：如何确保表格在 PDF 文档的所有页面上一致显示？

答：当您使用`HeaderFooter`例如，Aspose.PDF 确保表格在每个页面上显示一致，提供统一的布局。