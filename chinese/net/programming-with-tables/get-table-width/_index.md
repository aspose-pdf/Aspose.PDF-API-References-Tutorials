---
title: 获取表格宽度
linktitle: 获取表格宽度
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 获取 PDF 文档中表格的宽度。
type: docs
weight: 90
url: /zh/net/programming-with-tables/get-table-width/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 获取 PDF 文档中表格的宽度。我们将逐步解释 C# 中的源代码。在本教程结束时，您将了解如何获取 PDF 文档中表格的宽度。开始吧！

## 第 1 步：设置环境
首先，确保您已经使用 Aspose.PDF for .NET 设置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第 2 步：创建新文档和页面
我们新建一个PDF文档，并在这个文档中添加一个页面。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 3 步：初始化新表
我们初始化一个新表并将适合的列设置为“AutoFitToContent”。

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## 第 4 步：在表格中添加行和单元格
我们在表中添加一行并在该行中添加单元格。

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## 第 5 步：获取表格宽度
我们使用“GetWidth()”方法来获取表格的宽度。

```csharp
Console.WriteLine(table.GetWidth());
```

### 使用 Aspose.Words for .NET 获取表格宽度的示例源代码

```csharp
//创建一个新文档
Document doc = new Document();
//在文档中添加页面
Page page = doc.Pages.Add();
//初始化新表
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
//在表中添加行
Row row = table.Rows.Add();
//在表格中添加单元格
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
//获取表格宽度
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文档中表格的宽度。您可以使用此分步指南在您自己的 C# 项目中获取表格宽度。