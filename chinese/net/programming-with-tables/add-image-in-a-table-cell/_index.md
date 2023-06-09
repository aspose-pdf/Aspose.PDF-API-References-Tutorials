---
title: 在表格单元格中添加图像
linktitle: 在表格单元格中添加图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在表格单元格中添加图像，这是对 PDF 文档中的图像进行精确操作的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-tables/add-image-in-a-table-cell/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将图像添加到表格单元格的过程。提供的 C# 源代码演示了如何实现此功能。按照下面列出的步骤，您将能够有效地将图像合并到表格单元格中。

在我们深入研究代码之前，请确保您的项目中安装并引用了 Aspose.PDF for .NET 库。

## 第 1 步：设置文档

首先，我们需要创建一个新的实例`Document`来自 Aspose.Pdf 命名空间的类。此类表示 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化一个文档对象
Document pdfDocument = new Document();
```

## 第 2 步：创建页面

接下来，我们需要在 PDF 文档中添加一个页面。页面充当表格和其他元素的容器。

```csharp
//在pdf文档中创建一个页面
Page sec1 = pdfDocument.Pages.Add();
```

## 第 3 步：添加表格

在这一步中，我们将通过实例化`Table`来自 Aspose.Pdf 命名空间的类。

```csharp
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 第 4 步：设置默认单元格边框

为了确保一致性，我们可以使用`DefaultCellBorder`表的属性`BorderInfo`目的。

```csharp
//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 第 5 步：设置列宽

要定义表格中每一列的宽度，我们可以设置`ColumnWidths`财产。将宽度指定为具有空格分隔值的字符串。

```csharp
//设置表格的列宽
tab1.ColumnWidths = "100 100 120";
```

## 第 6 步：将图像添加到表格单元格

现在是激动人心的部分，将图像添加到表格单元格。为此，我们将遵循以下子步骤：

## 步骤 6.1：创建图像对象

创建一个实例`Image`来自 Aspose.Pdf 命名空间的类。设置`File`属性添加到要添加的图像文件的路径。

```csharp
//创建图像对象
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## 步骤 6.2：创建行和单元格

要将图像添加到表格中，我们首先需要创建一行和必要的单元格。

```csharp
//在表中创建一行
Aspose.Pdf.Row row1 = tab1.Rows.Add();

//向行中添加一个文本单元格
row1.Cells.Add("Sample text in cell");

//添加保存图像的单元格
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## 步骤 6.3：将图像添加到表格单元格

最后，我们可以通过将图像作为段落添加到单元格中来将图像添加到表格单元格中。

```csharp
//将图像添加到表格单元格
cell2.Paragraphs.Add(img);
```

## 步骤 6.4：添加其他单元格

添加图像单元格后，如果需要，我们可以向行添加更多单元格。

```csharp
//向该行添加另一个单元格
row1.Cells.Add("Previous cell with image");

//调整第三个单元格的垂直对齐方式
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## 第 7 步：保存文件

最后，我们可以使用`Save`方法。

```csharp
//保存文件
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

恭喜！您已经成功学习了如何使用 Aspose.PDF for .NET 将图像添加到表格单元格。随意探索更多自定义选项并将此功能集成到您的项目中。

### 使用 Aspose.PDF for .NET 在表格单元格中添加图像的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化一个文档对象
Document pdfDocument = new Document();
//在pdf文档中创建一个页面
Page sec1 = pdfDocument.Pages.Add();
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//在所需页面的段落集合中添加表格
sec1.Paragraphs.Add(tab1);
//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//设置表格的列宽
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
//添加保存图像的单元格
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
//将图像添加到表格单元格
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
//保存文件
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## 结论

在本教程中，我们介绍了如何使用 Aspose.PDF for .NET 将图像添加到表格单元格的分步指南。我们从设置文档、创建页面和添加表格开始。然后，我们设置默认的单元格边框和列宽。我们演示了如何将图像添加到表格单元格并调整单元格的垂直对齐方式。最后，我们保存修改后的文档。通过执行这些步骤，您可以使用表格单元格中的图像有效地增强 PDF 文档。