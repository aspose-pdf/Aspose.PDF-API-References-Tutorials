---
title: 在现有 PDF 中标记图像
linktitle: 在现有 PDF 中标记图像
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 标记现有 PDF 中的图像。向图像添加标签的分步指南。
type: docs
weight: 210
url: /zh/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
在本详细教程中，我们将逐步指导您使用提供的 C# 源代码，使用 Aspose.PDF for .NET 标记现有 PDF 中的图像。按照以下说明了解如何向 PDF 中的图像添加标签。

## 步骤 1：设置环境

开始之前，请确保您已将开发环境配置为使用 Aspose.PDF for .NET。这包括安装 Aspose.PDF 库并配置您的项目以引用它。

## 第 2 步：打开现有 PDF 文档

在此步骤中，我们将使用 Aspose.PDF 打开一个现有的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//输入和输出文件路径
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//打开文档
Document document = new Document(inFile);
```

我们使用 Aspose.PDF 打开了现有的 PDF 文档。

## 步骤3：获取标记内容和根结构元素

现在我们将获取PDF文档的标记内容和相应的根结构元素。

```csharp
//获取标记内容和根结构元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

我们得到了PDF文档的标记内容和相应的根结构元素。

## 步骤 4：设置标记 PDF 文档的标题

现在让我们为标记的 PDF 文档设置标题。

```csharp
//定义标记的 PDF 文档的标题
taggedContent.SetTitle("Document with images");
```

我们已经为标记的 PDF 文档设置了标题。

## 步骤 5：为图像分配替代文本和边界框

现在，对于每个图像元素，我们将分配替代文本和边界框。

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     //为图像指定替代文本
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     //创建并分配边界框（bbox）
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

我们为 PDF 文档中的每个图像元素分配了替代文本和边界框。

## 步骤 6：将 Span 元素移入段落

现在让我们将 Span 元素移到段落中。

```csharp
//将 Span 元素移入段落（在第一个 TD 中查找不正确的 span 和段落）
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//移动段落中的 Span 元素
spanElement.ChangeParentElement(paragraph);
```

我们将 Span 元素移到了指定的段落中。

## 步骤 7：保存修改后的 PDF 文档

现在我们已经做出了必要的更改，我们将保存修改后的 PDF 文档。

```csharp
//保存 PDF 文档
document. Save(outFile);
```

我们将修改后的PDF文档保存在指定的目录中。

### 使用 Aspose.PDF for .NET 在现有 PDF 中标记图像的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//打开文档
Document document = new Document(inFile);

//获取标记内容和根结构元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

//设置标记的 PDF 文档的标题
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	//设置图形的替代文本
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	//创建并设置 BBox 属性
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

//将跨度元素移入段落（在第一个 TD 中查找错误的跨度和段落）
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//将 Span 元素移入段落
spanElement.ChangeParentElement(paragraph);

//保存文档
document.Save(outFile);

//检查文档的 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 标记现有 PDF 中的图像。现在，您可以使用 Aspose.PDF 添加标签并编辑 PDF 文档中的图像。

### 常见问题解答

#### 问：本教程关于使用 Aspose.PDF for .NET 标记现有 PDF 中的图像的主要目的是什么？

答：本教程的主要目标是指导您使用 Aspose.PDF for .NET 在现有 PDF 文档中标记图像的过程。本教程提供分步说明和 C# 源代码示例，以帮助您了解如何为图像分配替代文本和边界框、在文档内移动元素以及向图像添加标签。

#### 问：按照本教程使用 Aspose.PDF for .NET 在 PDF 中标记图像的先决条件是什么？

答：开始之前，请确保您已设置开发环境以使用 Aspose.PDF for .NET。这涉及安装 Aspose.PDF 库并配置您的项目以引用它。

#### 问：如何使用 Aspose.PDF for .NET 打开现有的 PDF 文档并访问其标记内容？

答：本教程提供了 C# 源代码示例，演示如何使用 Aspose.PDF for .NET 打开现有 PDF 文档并访问其标记内容以进行进一步操作。

#### 问：为 PDF 文档中的图像分配替代文本和边界框的目的是什么？

答：为图像指定替代文本和边界框可通过为图像提供描述性文本并定义其在文档中的布局和位置来增强可访问性。此信息对于屏幕阅读器和其他辅助技术至关重要。

#### 问：如何使用 Aspose.PDF for .NET 设置标记的 PDF 文档的标题？

答：本教程包括 C# 源代码示例，说明如何使用 Aspose.PDF for .NET 为标记的 PDF 文档设置标题。

#### 问：在 PDF 文档中移动元素的过程涉及什么？

答：在 PDF 文档中移动元素涉及更改特定元素的父元素。在本教程中，您将学习如何将 Span 元素移动到表格中的指定 Paragraph 元素中。

#### 问：添加标签和编辑图像后，如何保存修改后的 PDF 文档？

答：添加标签、指定替代文本、设置边界框并对 PDF 文档进行编辑后，您可以使用提供的 C# 源代码示例，使用`Save()`方法。

#### 问：教程中提供的示例源代码有何用途？

答：示例源代码可作为使用 Aspose.PDF for .NET 实现图像标记和处理的实用参考。您可以使用此代码作为起点，并对其进行修改以满足您的特定要求。

#### 问：我可以将这些技术应用于 PDF 文档中的其他类型元素，而不仅仅是图像吗？

答：是的，本教程中演示的技术可以适用于 PDF 文档中的各种元素。您可以应用类似的原理来标记和操作其他元素，例如文本、表格等。

#### 问：如何验证修改后的 PDF 文档是否符合 PDF/UA 标准？

答：本教程提供了 C# 源代码示例，展示了如何使用`Validate()`方法并生成 XML 报告。

#### 问：Aspose.PDF for .NET 还提供哪些其他用于处理 PDF 文档的功能？

答：Aspose.PDF for .NET 提供了多种处理 PDF 文档的功能，包括文本处理、图像插入、表格创建、表单字段管理、数字签名、注释等。请查阅官方文档和资源以进一步探索。