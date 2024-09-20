---
title: 样式表单元格
linktitle: 样式表单元格
second_title: Aspose.PDF for .NET API 参考
description: 通过本详细教程学习如何使用 Aspose.PDF for .NET 设置 PDF 中表格单元格的样式。按照说明创建和格式化漂亮的 PDF 表格。
type: docs
weight: 160
url: /zh/net/programming-with-tagged-pdf/style-table-cell/
---
## 介绍

创建具有专业外观的 PDF 表格可能很棘手，但使用 Aspose.PDF for .NET，这非常简单！无论您是设置页眉、页脚还是特定表格单元格的样式，这个功能强大的库都为您提供了创建格式精美的 PDF 文档所需的所有工具。在本教程中，我们将介绍如何使用 Aspose.PDF for .NET 设置 PDF 文档中的表格单元格的样式。别担心——我们会将所有内容分解为易于遵循的步骤。

## 先决条件

在深入研究代码之前，请确保您满足以下先决条件：

1. Aspose.PDF for .NET：从以下网址下载并安装最新版本的 Aspose.PDF[这里](https://releases.aspose.com/pdf/net/).
2. IDE（如 Visual Studio）：设置 .NET 开发环境。
3. C# 编程基础知识：需要对 C# 有一定熟悉。
4.  Aspose.PDF 许可证：获取临时或完整许可证以解锁库的全部功能。您可以免费试用[这里](https://purchase.aspose.com/temporary-license/).

## 导入包

开始之前，请确保导入必要的命名空间。您的项目中需要以下内容：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

现在一切都已设置好，让我们进入分步指南！

我们将在 PDF 文档中创建表格并设置其单元格的样式。每个步骤都会详细说明该过程。

## 步骤 1：创建新的 PDF 文档

第一步是创建一个新的 PDF 文档。在 Aspose.PDF 中，您可以初始化一个新的`Document`对象，代表您的 PDF 文件。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建新的 PDF 文档
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

在这里，我们初始化 PDF 文档并设置其标题和语言。这为您的文档提供了适当的结构，这对于符合 PDF/UA 规范至关重要。

## 第 2 步：设置表结构

PDF 中的表格在结构元素内定义。让我们创建表格并定义表格的行和列。

```csharp
//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;

//创建表结构元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

现在我们已经定义了表头（`TableTHeadElement`）， 身体 （`TableTBodyElement`) 和脚 (`TableTFootElement`) 部分。您可以将它们视为表格的骨架。

## 步骤 3：设置标题单元格的样式

对标题单元格进行样式设置，使其更加突出。在这里，我们应用背景颜色、边框和文本对齐方式。

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

在此步骤中，我们循环遍历每个标题单元格，为其添加绿黄色背景、灰色边框和右对齐文本。您可以调整这些属性以匹配所需的设计。

## 步骤 4：填充表体并设置其样式

表格主体包含实际数据。下面介绍如何使用特定边距、边框和文本设置来设置每个单元格的样式。

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

在此步骤中，我们将表格主体填充为四行，并将每个单元格设置为黄色背景和居中、粗体蓝色文本。我们还使用`MarginInfo`类来定义文本周围的填充。

## 步骤 5：设置页脚样式

为了使表格具有完整的结构，我们添加并设置页脚单元格的样式，就像我们对页眉所做的那样。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

页脚部分的样式与页眉类似，方便读者了解表格的结构。

## 步骤 6：保存并验证 PDF 文档

最后，我们保存 PDF 文档并检查它是否符合 PDF/UA 标准。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "StyleTableCell.pdf");

//检查 PDF/UA 合规性
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

我们保存 PDF 并使用`Validate`方法来确保它符合可访问性标准（PDF/UA 合规性）。

## 结论

使用 Aspose.PDF for .NET 为 PDF 中的表格设置样式既强大又灵活。只需几行代码，您就可以创建自定义表格设计，让您的 PDF 文档脱颖而出。从自定义单元格边框和背景到确保可访问性合规性，Aspose.PDF 让您可以轻松创建精美的 PDF 文件。

## 常见问题解答

### 我可以对各个表格单元格应用不同的样式吗？  
是的，您可以通过自定义`TableTDElement`特性。

### 如何合并表格单元格？  
您可以使用`ColSpan`和`RowSpan`属性来合并表中的单元格。

### 是否可以创建符合 PDF/UA 标准的表格？  
是的，如本指南所示，您可以通过使用以下方式验证文档，以确保符合 PDF/UA 要求：`Validate`方法。

### 我可以在表格单元格中使用不同的字体吗？  
当然可以！您可以使用`TextState`每个单元格的对象。

### 如何下载适用于 .NET 的 Aspose.PDF？  
您可以从[发布页面](https://releases.aspose.com/pdf/net/).