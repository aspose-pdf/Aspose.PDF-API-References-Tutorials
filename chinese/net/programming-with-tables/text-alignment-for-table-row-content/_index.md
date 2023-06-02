---
title: 表行内容的文本对齐方式
linktitle: 表行内容的文本对齐方式
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 对齐 PDF 表格中的行内容。
type: docs
weight: 210
url: /zh/net/programming-with-tables/text-alignment-for-table-row-content/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 逐步对齐 PDF 文档表格中行的内容。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：创建 PDF 文档
首先，我们将创建 PDF 文档：

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 第二步：表初始化
接下来，我们将初始化表：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 第三步：设置表格边框颜色
我们将配置表格边框颜色：

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 第 4 步：配置表格单元格边框
我们将配置表格单元格边框：

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 第 5 步：循环向表中添加 10 行
我们现在将使用循环向表中添加 10 行：

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## 第 6 步：配置垂直线对齐
我们将配置表格行的垂直对齐方式：

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## 第 7 步：向行单元格添加内容
我们将向行单元格添加内容：

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## 第 8 步：将表格添加到文档页面
现在让我们将表格添加到文档页面：

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## 步骤 9：保存 PDF 文档
最后，我们将保存 PDF 文档：

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### 使用 Aspose.Words for .NET 的表格行内容文本对齐示例源代码

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 PDF 文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//初始化 Table 的新实例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//将表格边框颜色设置为 LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//设置表格单元格的边框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//创建一个循环以添加 10 行
for (int row_count = 0; row_count < 10; row_count++)
{
	//向表中添加行
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
//将表格对象添加到输入文档的第一页
tocPage.Paragraphs.Add(table);
//保存包含表格对象的更新文档
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 结论
恭喜！您现在已经学习了如何使用 Aspose.PDF for .NET 对齐 PDF 文档中表格中行的内容。本分步指南向您展示了如何创建文档、初始化表格、配置边框和对齐方式、添加内容以及保存 PDF 文档。现在您可以将这些知识应用到您自己的项目中。