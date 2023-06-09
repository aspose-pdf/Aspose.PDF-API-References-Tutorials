---
title: 在现有 PDF 中标记图像
linktitle: 在现有 PDF 中标记图像
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在现有 PDF 中标记图像。向图像添加标签的分步指南。
type: docs
weight: 210
url: /zh/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
在这个详细的教程中，我们将逐步引导您完成提供的 C# 源代码，以使用 Aspose.PDF for .NET 在现有 PDF 中标记图像。按照以下说明了解如何向 PDF 中的图像添加标签。

## 第 1 步：设置环境

在开始之前，请确保您已将开发环境配置为使用 Aspose.PDF for .NET。这包括安装 Aspose.PDF 库和配置您的项目以引用它。

## 第 2 步：打开现有的 PDF 文档

在此步骤中，我们将使用 Aspose.PDF 打开现有的 PDF 文档。

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

我们使用 Aspose.PDF 打开现有的 PDF 文档。

## 第 3 步：获取标记内容和根结构元素

现在我们将获取 PDF 文档的标记内容和相应的根结构元素。

```csharp
//获取标记内容和根结构元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

我们得到了PDF文档的标记内容和对应的根结构元素。

## 第 4 步：为带标签的 PDF 文档设置标题

现在让我们为标记的 PDF 文档设置标题。

```csharp
//定义带标签的 PDF 文档的标题
taggedContent.SetTitle("Document with images");
```

我们已经为标记的 PDF 文档设置了标题。

## 第 5 步：为图像分配替代文本和边界框

现在，我们将为每个图像元素分配替代文本和边界框。

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     //为图像分配替代文本
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     //创建和分配边界框 (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

我们为 PDF 文档中的每个图像元素分配了替代文本和边界框。

## 第 6 步：将 Span 元素移动到段落中

现在让我们将 Span 元素移动到段落中。

```csharp
//将跨度元素移动到段落中（在第一个 TD 中找到不正确的跨度和段落）
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//移动段落中的 Span 元素
spanElement.ChangeParentElement(paragraph);
```

我们将 Span 元素移动到指定的段落中。

## 步骤 7：保存修改后的 PDF 文档

现在我们已经进行了必要的更改，我们将保存修改后的 PDF 文档。

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

//获取标记的内容和根结构元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

//为标记的 pdf 文档设置标题
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	//为图设置替代文本
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	//创建和设置 BBox 属性
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

//将跨度元素移动到段落中（在第一个 TD 中找到错误的跨度和段落）
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//将 Span 元素移动到段落中
spanElement.ChangeParentElement(paragraph);

//保存文档
document.Save(outFile);

//检查输出文档的 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在现有 PDF 中标记图像。您现在可以使用 Aspose.PDF 添加标签并对 PDF 文档中的图像进行编辑。
