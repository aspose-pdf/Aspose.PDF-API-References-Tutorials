---
title: 添加 SVG 对象
linktitle: 添加 SVG 对象
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地将 SVG 对象添加到您的 PDF 文件。
type: docs
weight: 30
url: /zh/net/programming-with-tables/add-svg-object/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 库将 SVG 对象添加到 PDF 文件。 SVG（可缩放矢量图形）是一种流行的矢量图形格式，可以轻松缩放而不会降低质量。使用 Aspose.PDF，您可以通过编程方式将 SVG 对象添加到您的 PDF 文档中。

## 要求

在我们开始之前，请确保您拥有以下内容：

- 安装了 Visual Studio
- 已安装 Aspose.PDF for .NET 库

## 第 1 步：设置环境

首先，让我们通过在 Visual Studio 中创建一个新的 C# 项目来设置环境。打开 Visual Studio 并执行以下步骤：

1. 单击“文件”>“新建”>“项目”创建一个新项目。
2. 根据您的设置，选择“控制台应用程序 (.NET Framework)”或“控制台应用程序 (.NET Core)”模板。
3. 为您的项目选择合适的名称和位置，然后单击“创建”。

## 第 2 步：创建文档和图像对象

在此步骤中，我们将为 PDF 文档和 SVG 图像创建必要的对象。打开项目的 C# 文件并添加以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//即时文档对象
Document doc = new Document();
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## 第 3 步：设置图像属性

接下来，我们将为 SVG 图像设置属性。我们将文件类型指定为 SVG、SVG 文件的路径以及图像的尺寸。在上一步之后添加以下代码：

```csharp
//将图像类型设置为 SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//源文件路径
img.File = dataDir + "SVGToPDF.svg";
//设置图像实例的宽度
img. FixWidth = 50;
//设置图像实例的高度
img.FixHeight = 50;
```

## 第 4 步：创建和配置表

现在，让我们创建一个表格对象并设置列宽。我们将创建一个包含两列的表格，每列的宽度为 100 个单位。添加以下代码：

```csharp
//创建实例表
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//设置表格单元格的宽度
table. ColumnWidths = "100 100";
```

## 第 5 步：将单元格添加到表中

在此步骤中，我们将向表中添加一行和单元格。每行代表表格中的水平行，单元格添加到行中。添加以下代码：

```csharp
//创建行对象并将其添加到表实例
Aspose.Pdf.Row row = table.Rows.Add();
//创建单元格对象并将其添加到行实例
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## 第 6 步：将文本和图像添加到单元格

接下来，让我们将文本和 SVG 图像添加到表格的单元格中。我们会将文本“First cell”添加到第一个单元格，将 SVG 图像添加到第二个单元格。添加以下代码：

```csharp
//将文本片段添加到单元格对象的段落集合
cell.Paragraphs.Add(new TextFragment("First cell"));
//将另一个单元格添加到行对象
cell = row. Cells. Add();
//将 SVG 图像添加到最近添加的单元格实例的段落集合
cell.Paragraphs.Add(img);
```

## 第 7 步：创建页面并将其添加到文档

现在，让我们创建一个页面对象并将其添加到文档中。该表将添加到页面的段落集合中。添加以下代码：

```csharp
//创建页面对象并将其添加到文档实例的页面集合中
Page page = doc.Pages.Add();
//将表添加到页面对象的段落集合
page.Paragraphs.Add(table);
```

## 步骤 8：保存 PDF 文件

最后，我们将PDF文件保存到指定位置。添加以下代码：

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
//保存PDF文件
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 添加 SVG 对象的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档对象
Document doc = new Document();
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//将图像类型设置为 SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
//源文件路径
img.File = dataDir + "SVGToPDF.svg";
//设置图像实例的宽度
img.FixWidth = 50;
//设置图像实例的高度
img.FixHeight = 50;
//创建表实例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//设置表格单元格的宽度
table.ColumnWidths = "100 100";
//创建行对象并将其添加到表实例
Aspose.Pdf.Row row = table.Rows.Add();
//创建单元格对象并将其添加到行实例
Aspose.Pdf.Cell cell = row.Cells.Add();
//将文本片段添加到单元格对象的段落集合
cell.Paragraphs.Add(new TextFragment("First cell"));
//将另一个单元格添加到行对象
cell = row.Cells.Add();
//将 SVG 图像添加到最近添加的单元格实例的段落集合
cell.Paragraphs.Add(img);
//创建页面对象并将其添加到文档实例的页面集合中
Page page = doc.Pages.Add();
//将表添加到页面对象的段落集合
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
//保存PDF文件
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 库将 SVG 对象添加到 PDF 文件。我们介绍了创建文档、设置环境、将 SVG 图像添加到表格单元格以及保存 PDF 文件的分步过程。现在您可以通过编程将 SVG 对象合并到 PDF 文档中。