---
title: 样式表行
linktitle: 样式表行
second_title: Aspose.PDF for .NET API 参考
description: 通过分步指南学习如何使用 Aspose.PDF for .NET 设置 PDF 中表格行的样式，轻松增强文档格式。
type: docs
weight: 180
url: /zh/net/programming-with-tagged-pdf/style-table-row/
---
## 介绍

在创建结构良好、格式优美的 PDF 文档时，Aspose.PDF for .NET 是一个不错的解决方案。无论您是自动生成报告、发票还是创建动态表格，使用各种样式格式化表格都是制作精美文档的关键。在本教程中，我们将深入研究如何使用 Aspose.PDF for .NET 来设置表格行的样式。别担心，我会一步一步指导您，就像喝咖啡时的愉快交谈一样！

## 先决条件

在开始讨论细节之前，让我们先确保你已经做好了一切准备。你需要：

1. Aspose.PDF for .NET 库  
   如果你还没有，你可以从[这里](https://releases.aspose.com/pdf/net/)。您还可以获得[免费试用](https://releases.aspose.com/)开始吧。
2. 开发环境  
   设置 Visual Studio 或您选择的任何 C# IDE。您还需要安装 .NET，但我猜您已经很熟悉它了。
3. C# 和 .NET 的基础知识  
   充分理解 C# 将使本教程变得轻而易举。但别担心，我会详细解释每个步骤！

## 导入包

在开始使用 Aspose.PDF 之前，我们需要导入必要的命名空间。在您的 C# 项目中，请确保包含以下内容：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这些对于创建和设计表格以及处理标记内容以达到合规性至关重要。

现在让我们一步一步地分解任务，以便您可以像专业人士一样设置表格行的样式！

## 步骤 1：创建新的 PDF 文档

首先，让我们创建一个全新的 PDF 文档。此文档将保存所有样式化的表格行。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建文档
Document document = new Document();
```

这里我们只是初始化一个新的`Document`代表 PDF 文件的对象。请确保设置保存输出文件的目录路径。

## 第 2 步：处理标记内容

为了构建您的 PDF 以实现可访问性，我们将使用标记内容。这有助于创建表格等结构化元素，确保它们符合 PDF/UA 等可访问性标准。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

在这里，我们为 PDF 的标记内容设置标题和语言。这就像给你的 PDF 起个名字，并告诉它应该使用什么语言！

## 步骤 3：定义表结构

接下来，让我们定义即将创建的表格的结构。每个表格都需要一个页眉、正文和页脚 - 就像组织良好的博客文章一样！

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

我们在这里做的是创建一个带有标题的表格（`THead`）， 身体 （`TBody`) 和页脚 (`TFoot`）。这些元素将保存我们的行。

## 步骤 4：添加表头行

没有标题的表格就像没有标题的书。让我们先创建标题行来提供数据上下文。

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

在这里，我们循环并添加三个标题单元格 (`TableTHElement`)，为每个标签提供描述性文字。很简单，对吧？

## 步骤 5：添加样式化的正文行

现在到了最有趣的部分——设置行样式！让我们创建七行自定义样式。我们将设置背景颜色、边框、内边距和文本对齐方式。

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- 背景颜色：我们使用了浅金黄色，以营造专业而又温暖的感觉。
- 边框：每行都有深灰色外边框和蓝色单元格边框，以获得清晰的外观。
- 高度和填充：设置行高，并添加填充以获得整洁的外观。
- 分页符：为了使表格更具可读性，每隔一行都从新的一页开始。

## 步骤 6：添加页脚行

与表头类似，表尾固定表格。让我们创建一个表尾。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

我们只需循环遍历三个页脚单元格并添加一些文本即可。页脚的替代文本是“Foot Row”，以使其易于访问。

## 步骤 7：保存 PDF 文档

现在桌子已经全部设置好了，是时候保存你的杰作了！

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

就这样，您的 PDF 就保存了，其中包含我们刚刚设置样式的所有漂亮的表格行。

## 步骤 8：验证 PDF/UA 合规性

为了确保我们的 PDF 符合可访问性标准，我们将验证其是否符合 PDF/UA 标准。

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

这可确保您的 PDF 符合 PDF/UA 标准，让每个人都可以访问。可访问性才是关键！

## 结论

就这样！只需几行代码，您就可以使用 Aspose.PDF for .NET 在 PDF 中创建完整样式的表格。从页眉到页脚，我们设计了每一行的样式，添加了可访问性元素，甚至验证了文档的合规性。无论您是在处理公司报告、演示文稿，还是只是玩 PDF，本指南都能满足您的需求。现在，继续像专业人士一样设计您的表格样式吧！

## 常见问题解答

### 我也可以更改表格的字体样式吗？  
是的！您可以使用`TextState`每个单元格的对象，允许完全自定义。

### 如何向表中添加更多列？  
只需调整`colCount`变量并在页眉、正文和页脚的循环中添加更多单元格。

### 如果我不设置行高会发生什么？  
如果不设置行高，表格将根据内容自动调整。

### 我可以将其用于动态行数吗？  
当然可以！您可以从数据库或任何其他来源获取数据，并动态调整行数和列数。

### Aspose.PDF for .NET 可以免费使用吗？  
 Aspose.PDF for .NET 是一款授权产品，但你可以尝试使用[免费试用](https://releases.aspose.com/)或者得到[临时执照](https://purchase.aspose.com/temporary-license/).