---
title: 在现有 PDF 中标记图像
linktitle: 在现有 PDF 中标记图像
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 标记现有 PDF 中的图像。分步指南，通过 PDF/UA 合规性增强可访问性。
type: docs
weight: 210
url: /zh/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## 介绍

在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 标记现有 PDF 中的图像。在本指南结束时，您将能够为图像设置替代文本、调整布局属性并确保您的 PDF 符合可访问性标准。

## 先决条件

在深入研究之前，让我们先了解一下入门所需的条件：

-  Aspose.PDF for .NET：确保您已下载并安装了最新版本的 Aspose.PDF for .NET。[点击此处下载](https://releases.aspose.com/pdf/net/).
- .NET Framework：确保您已设置像 Visual Studio 这样的 .NET 开发环境。
- 对 PDF 结构的基本了解：熟悉 PDF 结构元素，例如段落、跨度、表格和图像。
- 有效许可证：您可以购买许可证[这里](https://purchase.aspose.com/buy)或者使用临时的[这里](https://purchase.aspose.com/temporary-license/).

## 导入包

要开始编码，您需要从 Aspose.PDF for .NET 导入必要的命名空间。这些将使您能够访问操作 PDF 文档所需的类和方法。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

现在我们已经做好了准备，让我们将标记图像的过程分解为多个步骤。

## 步骤 1：加载现有 PDF 文档

第一步是加载您要处理的 PDF 文件。这可以是任何带有您要标记的图像的 PDF 文件。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//打开文档
Document document = new Document(inFile);
```

- 代替`"YOUR DOCUMENT DIRECTORY"`使用您的文件的实际路径。
- 这`Document`类允许您加载现有 PDF。您将修改此 PDF 以标记图像。

## 第 2 步：访问标记内容和根结构元素

打开 PDF 后，下一步是访问标记内容并识别根结构元素。这很重要，因为它允许您浏览 PDF 中的元素并进行修改。

```csharp
//获取标记内容和根结构元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent`提供对 PDF 中结构化元素的访问。
- 这`RootElement`是最顶层的结构元素，您可以从这里向下遍历到其他元素，如段落、表格和图像。

## 步骤 3：设置带标签的 PDF 文档的标题

为标记的 PDF 文档添加标题可确保您的文档被正确标记，这有助于可访问性和 PDF/UA 合规性。

```csharp
//设置标记的 PDF 文档的标题
taggedContent.SetTitle("Document with images");
```

- 为标记的 PDF 设置标题可增强可访问性并提高屏幕阅读器和辅助技术的文档清晰度。

## 步骤 4：查找并标记图像

现在，让我们找到图像元素（称为`FigureElement`在Aspose.PDF中，为其设置替代文本，并配置其布局属性。

```csharp
//循环遍历所有图形元素（图像）并设置替代文本和布局属性
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    //设置图形的替代文本
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    //创建并设置 BBox 属性（边界框）
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    //设置图形的布局属性
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

- 此代码循环遍历所有`FigureElement`根结构中的对象，代表图像。
- 它设置了可访问性的替代文本（屏幕阅读器将使用它来描述图像）。
- 边界框（`BBox`指定图像布局的坐标，确保其在文档中正确显示。

## 步骤 5：修改表格内的 Span 元素

在某些情况下，您可能需要修改表格中的 span 元素。在这里，我们将演示如何查找`SpanElement`并将其移至段落中。

```csharp
//查找表格、跨度和段落元素
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//将 span 元素移至段落中
spanElement.ChangeParentElement(paragraph);
```

- 在这里，我们找到`TableElement`, `SpanElement`， 和`ParagraphElement`在 PDF 中。
- 使用`ChangeParentElement`方法，我们将跨度移到段落中以确保正确的标记和结构。

## 步骤 6：保存文档并验证 PDF/UA 合规性

完成所有更改后，最后一步是保存更新的 PDF 并检查它是否符合 PDF/UA 标准。

```csharp
//保存更新的 PDF 文档
document.Save(outFile);

//验证 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

- 这`Validate`方法根据 PDF/UA 标准检查 PDF 文档并记录结果。
- 确保合规性有助于提高可访问性并满足文档发布的监管要求。

## 结论

在本教程中，我们向您展示了如何使用 Aspose.PDF for .NET 标记现有 PDF 中的图像。通过设置替代文本、调整布局属性以及验证文档是否符合 PDF/UA 要求，您可以确保您的 PDF 可访问且符合现代标准。Aspose.PDF 让您可以轻松处理结构化元素，让您可以控制文档的布局和可访问性。

## 常见问题解答

### Aspose.PDF for .NET 用于什么用途？
Aspose.PDF for .NET 是一个功能强大的库，用于在.NET 环境中以编程方式创建、编辑和操作 PDF 文档。

### 如何确保符合 PDF/UA 要求？
您可以使用 Aspose.PDF 的`Validate`对文档进行修改后检查 PDF/UA 合规性的方法。

### PDF 中的替代文本是什么？
替代文本是添加到 PDF 中的图像的描述，以提高可访问性，特别是对于依赖屏幕阅读器的用户。

### 我可以使用 Aspose.PDF 操作 PDF 中的表格和跨度吗？
是的，Aspose.PDF 允许您操作 PDF 文档中的表格、跨度和其他结构化元素。

### 我可以在哪里下载 Aspose.PDF for .NET？
您可以下载最新版本的 Aspose.PDF for .NET[这里](https://releases.aspose.com/pdf/net/).