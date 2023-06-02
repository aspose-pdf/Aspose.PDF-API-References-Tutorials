---
title: 插入分页符
linktitle: 插入分页符
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中插入分页符。
type: docs
weight: 110
url: /zh/net/programming-with-tables/insert-page-break/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 在 PDF 文档中插入分页符。我们将逐步解释 C# 中的源代码。在本教程结束时，您将知道如何在 PDF 文档的表格中的一定行数后添加分页符。开始吧！

## 第 1 步：设置环境
确保您已经使用 Aspose.PDF for .NET 配置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第 2 步：创建文档和表格
我们创建一个新的 Document 实例并向该文档添加一个页面。接下来，我们创建一个 Table 实例来表示 PDF 文档中的表格。我们还定义了表格的边框样式。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## 第 3 步：向表中添加行
我们使用循环向数组添加 200 行。对于每一行，我们创建一个 Row 实例并添加两个包含文本内容的单元格。

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     //当添加 10 行时，我们插入一个新的分页符
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## 第 4 步：将表格添加到文档
我们将表格添加到文档页面的段落集合中。

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 第 5 步：保存文档
我们保存插入分页符的 PDF 文档。

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### 使用 Aspose.Words for .NET 插入分页符的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
doc.Pages.Add();
//创建表实例
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
//设置表格的边框样式
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//为表格设置默认边框样式，边框颜色为红色
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//指定表格列宽
tab.ColumnWidths = "100 100";
//创建一个循环为表添加 200 行
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	//添加 10 行时，在新页面中呈现新行
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
//将表格添加到 PDF 文件的段落集合
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中插入分页符。您可以使用此分步指南使用 C# 在 PDF 文档的表格中的特定行数之后添加分页符。