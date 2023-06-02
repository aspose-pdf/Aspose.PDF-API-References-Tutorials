---
title: 添加表
linktitle: 添加表
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地将表格添加到您的 PDF 文档。
type: docs
weight: 40
url: /zh/net/programming-with-tables/add-table/
---

Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、操作和转换 PDF 文档。在本教程中，我们将指导您完成使用 Aspose.PDF for .NET 向 PDF 文档添加表格的过程。我们将解释提供的代码片段的每个步骤，并提供全面的指南，帮助您理解和实现您自己项目中的功能。

## 介绍

PDF 文档广泛用于以便携式格式共享和保存信息。将表格添加到 PDF 文档可以增强其视觉外观，并使数据呈现更有条理和结构化。 Aspose.PDF for .NET 提供了一种方便的方法来将表格添加到现有的 PDF 文档或从头开始创建新的表格。

## 什么是 Aspose.PDF for .NET？

Aspose.PDF for .NET 是一个功能强大且功能丰富的库，它使 .NET 开发人员能够以编程方式创建、操作和转换 PDF 文档。它提供了广泛的功能，包括从头开始创建 PDF 文件、修改现有 PDF 文档、合并或拆分 PDF 文件、添加文本、图像和表格、从 PDF 中提取数据等等。使用 Aspose.PDF for .NET，开发人员可以自动执行复杂的 PDF 相关任务并提供高质量的 PDF 解决方案。

## 将表格添加到 PDF 文档

要使用 Aspose.PDF for .NET 将表格添加到 PDF 文档，请遵循以下分步指南：

## 第 1 步：加载源 PDF 文档

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

上面的代码片段加载了您要将表格添加到的源 PDF 文档。确保提供正确的 PDF 文件路径。

## 第 2 步：初始化 Table 的新实例

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

在此步骤中，我们创建 Table 类的一个新实例，它表示 PDF 文档中的表格。

## 第三步：设置表格边框颜色

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

在这里，我们使用 BorderInfo 类设置表格的边框颜色。您可以根据需要自定义边框样式、宽度和颜色。

## 第 4 步：设置表格单元格的边框

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

我们还使用表格对象的 DefaultCellBorder 属性设置表格单元格的边框。这可确保表格中的每个单元格都具有指定的边框样式、宽度和颜色。

## 第 5 步：向表中添加行和单元格

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

在此步骤中，我们创建一个循环以向表中添加 10 行。在每一行中，我们添加三个包含示例数据的单元格。您可以修改代码以根据您的特定要求添加行和单元格。

## 第 6 步：将表格对象添加到文档中

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
//保存包含表格对象的更新文档
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

最后，我们使用相应页面的 Paragraphs 集合将表格对象添加到 PDF 文档的第一页。

### 使用 Aspose.Words for .NET 添加表格的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载源 PDF 文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
//初始化 Table 的新实例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//将表格边框颜色设置为 LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//设置表格单元格的边框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//创建一个循环以添加 10 行
for (int row_count = 1; row_count < 10; row_count++)
{
	//向表中添加行
	Aspose.Pdf.Row row = table.Rows.Add();
	//添加表格单元格
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
//将表格对象添加到输入文档的第一页
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
//保存包含表格对象的更新文档
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## 结论

在本教程中，我们解释了使用 Aspose.PDF for .NET 向 PDF 文档添加表格的分步过程。我们介绍了加载源 PDF 文档、初始化 Table 类的新实例、设置表格边框颜色和单元格边框、向表格添加行和单元格以及向文档添加表格对象。通过遵循本指南，您可以轻松地以编程方式将表格合并到 PDF 文档中，并根据您的特定需要自定义它们。