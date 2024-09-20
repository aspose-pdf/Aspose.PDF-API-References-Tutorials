---
title: 在 PDF 文档中呈现表格
linktitle: 在 PDF 文档中呈现表格
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 渲染表格，轻松创建专业的 PDF。按照我们的分步指南掌握文档生成。
type: docs
weight: 170
url: /zh/net/programming-with-tables/render-table/
---
## 介绍

以编程方式创建具有专业外观的 PDF 似乎是一项艰巨的任务，但使用 Aspose.PDF for .NET，它变得轻而易举。无论您是生成报告、发票还是任何其他需要表格数据的文档类型，Aspose.PDF 都能提供您所需的工具。在本教程中，我们将逐步探索如何在 PDF 文档中呈现表格。到最后，您将对如何轻松操作表格、管理页面属性和保存 PDF 文件有一个扎实的理解。

## 先决条件

在我们深入研究代码之前，您需要满足以下条件：

-  Visual Studio：请确保您的计算机上安装了 Visual Studio。您可以下载它[这里](https://visualstudio.microsoft.com/downloads/).
- Aspose.PDF for .NET：您可以从[Aspose 发布页面](https://releases.aspose.com/pdf/net/).
- C# 基础知识：了解 C# 的基础知识将帮助您更好地跟进。
- .NET Framework：理想情况下，确保您在兼容的 .NET 环境中工作。

一旦设置了这些先决条件，您就可以开始创建 PDF 文档了！

## 导入包

在 C# 文件的开头，您需要导入必要的 Aspose.PDF 命名空间。这样您就可以在我们的项目中使用库功能。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

确保已在项目中添加对 Aspose.PDF 库的必要引用。如果您使用 NuGet，则可以通过搜索轻松添加`Aspose.PDF`.

现在我们已经设置好了一切，让我们将流程分解为几个可管理的步骤，以便在 PDF 文档中呈现表格。别担心；我会用清晰的说明引导您完成每个步骤！

## 步骤 1：设置文档和页面信息

首先，我们需要创建一个新文档并配置其页面设置。操作方法如下：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

解释： 
- 我们首先定义文档的保存位置（`dataDir`）。 
- 然后我们创建一个新的实例`Document`班级。 
- 我们配置页边距以在表格周围创建一些喘息空间。
- 最后，我们将文档设置为横向，这有助于显示更宽的表格。

## 步骤 2：创建第一个表

接下来，让我们创建第一个表并用一些示例数据填充它：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; //定义列宽
```

解释：在这里，我们实例化`Table`类并设置列宽。第一列的宽度为 50 个单位，第二列的宽度为 100 个单位。

## 步骤 3：用行填充表格

现在，让我们循环向表中添加行：

```csharp
Page curPage = doc.Pages.Add(); //添加新页面
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; //设置固定行高
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

解释： 
- 在这里我们创建一个新页面来添加我们的表格。
- 我们使用`for`循环向我们的表添加 120 行。每行的固定高度为 15 个单位。
- 在每一行内，我们添加两个单元格并用文本填充它们。

## 步骤 4：将第一个表添加到页面

一旦我们填充了表格，我们就会将其添加到当前页面：

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

解释：此步骤只是将我们创建的表格添加到当前页面的段落中，并使表格在 PDF 文档中可见。

## 步骤 5：创建第二个表

现在，让我们制作具有不同内容的第二个表格并将其添加到新页面：

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; //设置第二个表格出现在新页面上
paragraphs.Add(table1);
```

解释： 
- 此代码片段创建了一个有两列的新表，宽度均为 100 个单位。
- 一个`for`循环添加 10 行包含示例内容的行。
- 通过设置`table1.IsInNewPage`为真，我们确保该表出现在新页面上，使内容保持井然有序。

## 步骤 6：保存文档

现在我们的表格已经准备好了，让我们保存文档：

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

解释：我们指定文件名并将文档保存在定义的目录中。运行此代码时，将生成一个名为`IsNewPageProperty_Test_out.pdf`将在您指定的位置创建。

## 步骤 7：确认信息

最后，为了让用户知道一切顺利，我们可以添加一个友好的控制台消息：

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

说明：这是一种确认操作是否成功以及用户可以在哪里找到他们的新 PDF 文件的简单方法。

## 结论

就这样！您已成功使用 Aspose.PDF for .NET 在 PDF 文档中呈现表格。只需几行代码，您就可以以有组织的格式处理和呈现大量数据，使您的文档既信息丰富又具有视觉吸引力。无论您处理的是库存清单、财务报告还是教育文档，表格都是一目了然地传达复杂信息的绝佳方式。

## 常见问题解答

### 我可以自定义 Aspose.PDF 中表格的外观吗？  
当然可以！您可以调整颜色、边框、字体样式和其他属性来增强表格的外观。

### Aspose.PDF 可以免费使用吗？  
 Aspose.PDF 提供免费试用版，但若要用于商业用途，则需要购买。您可以查看定价[这里](https://purchase.aspose.com/buy).

### 我如何获得 Aspose.PDF 问题的支持？  
您可以从 Aspose 支持论坛寻求帮助[这里](https://forum.aspose.com/c/pdf/10).

### 免费试用版有什么限制吗？  
是的，试用版可能存在某些限制，例如生成的文档上会加水印。如需完整功能，请考虑获取临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 在哪里可以找到有关 Aspose.PDF 功能的更多信息？  
您可以探索可用的全面文档[这里](https://reference.aspose.com/pdf/net/).