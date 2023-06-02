---
title: 边距或填充
linktitle: 边距或填充
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在表格中设置边距或填充。
type: docs
weight: 140
url: /zh/net/programming-with-tables/margins-or-padding/
---

在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 在表格中设置边距或填充。我们将提供解释和代码片段，以帮助您理解并在 C# 源代码中实现此功能。

## 第 1 步：设置文档和页面
首先，您需要使用以下代码设置文档和页面：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Document 对象
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 2 步：创建表
接下来，我们将使用 Aspose.Pdf.Table 类创建一个表格对象：

```csharp
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//将表格添加到所需部分的段落集合
page.Paragraphs.Add(tab1);
```

## 第 3 步：设置列宽和默认单元格边框
要设置表格的列宽和默认单元格边框，请使用以下代码：

```csharp
//设置表格的列宽
tab1. ColumnWidths = "50 50 50";
//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 第四步：设置表格边框和单元格内边距
要设置表格边框和单元格填充，请创建一个 MarginInfo 对象并设置其属性：

```csharp
//创建一个 MarginInfo 对象并设置其左、下、右和上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

//将默认单元格填充设置为 MarginInfo 对象
tab1. DefaultCellPadding = margin;

//使用另一个自定义的 BorderInfo 对象设置表格边框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## 第 5 步：添加行和单元格
现在，让我们向表中添加行和单元格。我们将创建一个新行并向其中添加单元格：

```csharp
//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## 第 6 步：向单元格添加文本
要将文本添加到单元格，请创建一个 TextFragment 对象并将其添加到所需的单元格：

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## 第 7 步：保存 PDF
要保存 PDF 文档，请使用以下代码：

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//保存 PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.Words for .NET 的边距或填充示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Document 对象
Document doc = new Document();
Page page = doc.Pages.Add();
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//在所需部分的段落集合中添加表格
page.Paragraphs.Add(tab1);
//设置表格的列宽
tab1.ColumnWidths = "50 50 50";
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
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
//Row1.Cells.Add("col3 带有要放置在单元格内的大文本字符串");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//保存 PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## 结论
恭喜！您已经成功学习了如何使用 Aspose.PDF for .NET 在表格中设置边距或填充。这些知识将帮助您增强文档格式设置功能并使您的表格在视觉上更具吸引力。