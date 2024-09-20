---
title: 样式表元素
linktitle: 样式表元素
second_title: Aspose.PDF for .NET API 参考
description: 通过分步说明、自定义样式和 PDF/UA 兼容性了解如何在 Aspose.PDF for .NET 中创建和设置表格元素的样式。
type: docs
weight: 170
url: /zh/net/programming-with-tagged-pdf/style-table-element/
---
## 介绍

在本文中，我们将深入探讨如何使用 Aspose.PDF for .NET 创建和设置表格元素的样式。您将学习如何构造表格、应用自定义样式以及验证文档的 PDF/UA 合规性。在本教程结束时，您将能够轻松地在 PDF 中创建具有专业外观的表格！

## 先决条件

在进入本教程之前，您需要确保具备以下条件：

1. 您的机器上安装了 Visual Studio 或类似的 IDE。
2. 用于运行应用程序的 .NET Framework 或 .NET Core SDK。
3. 下载并引用了项目中的 Aspose.PDF for .NET 库。你可以从以下位置获取最新版本[这里](https://releases.aspose.com/pdf/net/).
4. 有效的 Aspose 许可证或[临时执照](https://purchase.aspose.com/temporary-license/)解锁该库的全部功能。

## 导入包

首先，将必要的命名空间导入到您的项目中：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这些命名空间涵盖核心 PDF 操作、标记内容、表格和文本格式。

现在让我们分解一下在 Aspose.PDF 中创建和设置表格样式的过程。我们将详细介绍每个部分，以便您可以跟进。

## 步骤 1：创建新的 PDF 文档并设置标记内容

在第一步中，我们将创建一个空白 PDF 文档并设置其标记内容。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建新的 PDF 文档
Document document = new Document();

//设置标记内容
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

我们首先创建一个新的`Document`对象，代表我们的 PDF。`TaggedContent`对象用于管理文档的结构，确保符合可访问性标准。我们设置文档的标题和语言，以便正确标记。

## 第 2 步：定义根元素

接下来，我们将创建根结构元素，它作为 PDF 中所有内容的容器。

```csharp
//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
```

这`RootElement`用作所有结构化元素（包括我们的表格）的基础容器。它有助于维护文档的结构层次，这对于组织和可访问性都很重要。

## 步骤 3：创建表格元素并设置其样式

现在根元素已经设置好了，我们将创建一个`TableElement`并应用背景颜色、边框和对齐等样式。

```csharp
//创建表结构元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

//设置表格样式
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

我们创建`TableElement`，它定义了我们的表结构。`BackgroundColor`, `Border`， 和`Alignment`属性允许我们自定义表格的外观。`Broken`属性确保如果表格跨页分页，则会垂直分页。

## 步骤 4：设置表格尺寸和单元格样式

在此步骤中，我们将定义列数、单元格填充和其他重要的表格属性。

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

我们指定列宽以确保表格中每列的间距均匀。`DefaultCellBorder`, `DefaultCellPadding`， 和`DefaultCellTextState`定义单元格的默认样式，包括边框、填充、文本颜色和字体大小。

## 步骤 5：添加重复行和自定义样式

我们还可以为重复行和其他特定表格元素（如页眉和页脚）定义样式。

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

这`RepeatingRowsCount`确保表格跨越多页时前三行重复。我们设置`RepeatingRowsStyle`将自定义背景颜色应用于这些行。

## 步骤 6：添加表头、表体和表脚元素

现在，让我们创建表格标题、正文和页脚部分并填充内容。

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

//创建标题行
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

//填充表体
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

表格分为三个部分：表头、表体和表尾。我们首先使用`TableTHElement`并添加列标题。然后，我们用以下代码填充表格主体：`TableTDElement`，用包含其位置的标签填充每个单元格。

## 步骤 7：保存文档

最后我们将PDF文档保存到指定的目录。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "StyleTableElement.pdf");
```

此步骤通过保存带有样式表的 PDF 文件来完成文档创建过程。

## 步骤 8：验证 PDF/UA 合规性

保存文档后，必须确保其符合 PDF/UA（通用辅助功能）标准。

```csharp
//检查 PDF/UA 合规性
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

在这里，我们重新加载文档并根据 PDF/UA 标准对其进行验证。合规性可确保您的 PDF 满足可访问性要求，使其适合广泛的用户。

## 结论

使用 Aspose.PDF for .NET，在 PDF 文档中创建和设置表格样式既简单又直观。按照本教程中概述的步骤，您可以构建具有自定义样式的表格并确保您的 PDF 符合可访问性标准。无论您是生成报告还是创建结构化文档，表格都是清晰呈现数据的强大工具。

## 常见问题解答

### 我可以在表格单元格内添加图像吗？
是的，您可以使用`Image`元素。

### 如何动态调整列宽？
您可以设置`ColumnAdjustment`财产`AutoFitToWindow`根据内容自动调整列宽。

### 所有文档都必须符合 PDF/UA 要求吗？
虽然不是强制性的，但对于需要高可访问性标准的文档建议使用它。

### 我可以对特定行应用不同的样式吗？
是的，您可以通过调整其`TextState`或者`BackgroundColor`.

### 使用标记内容有什么好处？
标记内容可提高文档的可访问性并有助于确保符合 PDF/UA 等标准。