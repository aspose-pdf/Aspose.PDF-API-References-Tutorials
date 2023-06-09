---
title: 设置边框
linktitle: 设置边框
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 表格中设置边框。
type: docs
weight: 200
url: /zh/net/programming-with-tables/set-border/
---

在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 在 PDF 文档的表格中设置边框。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：实例化 Document 对象
首先，我们将实例化一个 Document 对象：

```csharp
Document doc = new Document();
```

## 第 2 步：向 PDF 文档添加页面
接下来，我们将向 PDF 文档添加一个页面：

```csharp
Page page = doc.Pages.Add();
```

## 第 3 步：创建 BorderInfo 对象
我们现在将创建一个 BorderInfo 对象来定义表格的边框：

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## 第 4 步：指定顶部和底部边框
我们将指定顶部和底部边框为双边框：

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## 第 5 步：实例化 Table 对象
现在让我们实例化一个 Table 对象：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 第 6 步：指定列宽
我们将指定表格列的宽度：

```csharp
table. ColumnWidths = "100";
```

## 第 7 步：创建行对象
我们将创建一个 Row 对象：

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## 第 8 步：向行中添加一个单元格
接下来，我们将向该行添加一个单元格：

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## 第九步：设置单元格边框
我们将定义单元格的边框（双边框）：

```csharp
cell. Border = border;
```

## 第 10 步：将表格添加到页面
现在让我们将表格添加到文档页面：

```csharp
page.Paragraphs.Add(table);
```

## 步骤 11：保存 PDF 文档
最后，我们将保存 PDF 文档：

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 设置边框的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档对象
Document doc = new Document();
//将页面添加到 PDF 文档
Page page = doc.Pages.Add();
//创建 BorderInfo 对象
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//指定顶部边框为双边框
border.Top.IsDoubled = true;
//指定底部边框为双边框
border.Bottom.IsDoubled = true;
//实例化表对象
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//指定列宽信息
table.ColumnWidths = "100";
//创建行对象
Aspose.Pdf.Row row = table.Rows.Add();
//将表格单元格添加到行的单元格集合
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
//设置单元格对象的边框（双边框）
cell.Border = border;
//将表格添加到页面的段落集合
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## 结论
恭喜！您现在已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的表格中设置边框。本分步指南向您展示了如何创建文档、添加页面、配置表格边框和保存 PDF 文档。现在您可以将这些知识应用到您自己的项目中。