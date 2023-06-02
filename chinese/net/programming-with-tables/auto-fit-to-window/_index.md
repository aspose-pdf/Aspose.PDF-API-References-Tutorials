---
title: 自动适合窗口
linktitle: 自动适合窗口
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 并在生成 PDF 时自动适应窗口的分步指南。
type: docs
weight: 50
url: /zh/net/programming-with-tables/auto-fit-to-window/
---

以下文章是有关如何使用提供的 C# 源代码使用适用于 .NET 的 Aspose.PDF 库实现自动适合窗口功能的分步指南。自动适合窗口功能允许您生成布局适合查看窗口的 PDF 文件。当您希望 PDF 文档自动调整为用户使用的 PDF 阅读器窗口的大小时，此功能特别有用。

## 第 1 步：设置环境

在开始之前，您需要在您的机器上安装 .NET 的 Aspose.PDF 库。还要确保将必要的命名空间导入到您的项目中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建 PDF 文档

首先，您需要创建一个`Document`通过调用其默认构造函数来创建对象。

```csharp
Document doc = new Document();
```

接下来，在中创建一个部分`Pdf`目的。

```csharp
Page sec1 = doc.Pages.Add();
```

## 第 3 步：向文档添加表格

在这一步中，我们将向 PDF 文档中添加一个表格。首先创建一个`Table`目的。

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

接下来，将表格添加到该部分的段落集合中。

```csharp
sec1.Paragraphs.Add(tab1);
```

##  第 4 步：自定义表格外观

您可以通过设置单元格边框和边距等属性来自定义表格的外观。

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  第 4 步：向表中添加行和单元格

现在让我们向表中添加行和单元格。首先创建一行并向该行添加单元格。

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## 第 5 步：保存文档

最后，指定输出文件路径并保存文档。

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.Words for .NET 自动适应窗口的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Pdf 对象
Document doc = new Document();
//在 Pdf 对象中创建部分
Page sec1 = doc.Pages.Add();

//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//在所需部分的段落集合中添加表格
sec1.Paragraphs.Add(tab1);

//设置表格的列宽
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//使用另一个自定义的 BorderInfo 对象设置表格边框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//创建 MarginInfo 对象并设置其左、下、右和上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

//将默认单元格填充设置为 MarginInfo 对象
tab1.DefaultCellPadding = margin;

//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
//保存包含表格对象的更新文档
doc.Save(dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 生成具有自动适合窗口功能的 PDF 文件。当您希望 PDF 文档自动调整为查看窗口的大小时，此功能非常有用。 Aspose.PDF for .NET 提供了许多其他用于生成和操作 PDF 文件的强大功能。我鼓励您进一步探索这个库以发现它的所有功能。