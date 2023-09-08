---
title: 创建结构元素
linktitle: 创建结构元素
second_title: Aspose.PDF for .NET API 参考
description: 在本教程中，您将学习如何使用 Aspose.PDF for .NET 在标记的 PDF 文档中创建结构元素。
type: docs
weight: 60
url: /zh/net/programming-with-tagged-pdf/create-structure-elements/
---
以下 C# 源代码使用 Aspose.PDF for .NET 创建结构元素。请按照以下步骤了解代码的工作原理。

## 第1步：导入必要的库

```csharp
using Aspose.Pdf;
```

## 第 2 步：定义文档的目录

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必指定文档目录的正确路径。

## 步骤 3：创建 PDF 文档

```csharp
Document document = new Document();
```

我们创建一个新的 Document 对象来表示 PDF 文档。

## 第 4 步：获取可与 TaggedPdf 配合使用的内容

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

我们检索 PDF 文档的标记内容。这将使我们能够操纵结构元素。

## 第 5 步：设置文档标题和语言

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

我们设置带标签的 PDF 文档的标题和语言。这提高了文档的可访问性。

## 第 6 步：创建分组元素

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

我们创建不同的结构元素来对 PDF 文档中的内容进行分组。

## 步骤 7：创建段落结构元素

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

我们为段落和标题创建块级结构元素。上面的示例显示了 1 级标头的创建。

## 步骤 8：创建内联层级结构元素

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

我们为出现在段落或标题内的文本部分创建内联级别结构元素。

## 第 9 步：创建图稿结构元素

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

我们为文档中的插图和数学公式创建结构元素。

## 第10步：保存标记的PDF文档

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

我们使用创建的结构元素保存带标签的 PDF 文档。

### 使用 Aspose.PDF for .NET 创建结构元素的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 PDF 文档
Document document = new Document();
//获取与 TaggedPdf 一起使用的内容
ITaggedContent taggedContent = document.TaggedContent;
//设置文档网的标题和语言
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
//创建分组元素
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
//创建文本块级结构元素
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
//创建文本内联结构元素
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
//创建插图结构元素
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
//方法正在开发中
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
//保存标记的 PDF 文档
document.Save(dataDir + "StructureElements.pdf");

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在标记的 PDF 文档中创建结构元素。结构元素有助于提高文档的可访问性并以有意义的方式组织内容。现在，您可以使用这些知识来创建结构化、易于浏览的 PDF 文档。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 在 PDF 文档中创建结构元素的目的是什么？

答：使用 Aspose.PDF for .NET 在 PDF 文档中创建结构元素可以增强文档内容的可访问性和组织性。结构元素提供了分层结构，可改进导航、语义以及与辅助技术的兼容性。

#### 问：所提供的 C# 代码如何在 PDF 文档中创建结构元素？

答：代码示例演示了如何创建各种类型的结构元素，包括分组元素（如部件、节和 div）、块级元素（如段落和标题）、内联级元素（span、quote、note） ）和艺术元素（例如图形和公式）。这些结构元素有助于组织内容。

#### 问：为什么使用设置文档的标题和语言很重要`SetTitle` and `SetLanguage` methods?

A：使用设置文档的标题和语言`SetTitle`和`SetLanguage`方法提高了文档的可访问性和语义。标题提供了文档用途的简要描述，而语言属性则增强了特定于语言的呈现和可访问性。

#### 问：如何对元素进行分组，例如`PartElement` and `SectElement`, contribute to the structure of the PDF document?

答：对元素进行分组会在 PDF 文档中创建层次结构，使您能够逻辑地组织和分组相关内容。这增强了导航并为用户提供了清晰的结构。

#### 问：什么是块级和内联级结构元素，它们有何不同？

答：块级结构元素表示较大的内容块，例如段落和标题，而内联级元素表示段落或标题内的文本部分，例如跨度、引号和注释。它们帮助定义内容的层次结构和关系。

#### 问：艺术品如何构造元素，例如`FigureElement` and `FormulaElement`, contribute to the document?

答：图稿结构元素允许您向文档添加插图、图形和数学公式。它们提供了一种结构化的方式来包含视觉和数学内容。

#### 问：我可以使用类似的技术来创建其他类型的结构元素，例如列表、表格或注释吗？

答：是的，您可以使用类似的技术来创建其他类型的结构元素，例如列表、表格、注释、引用等。 Aspose.PDF提供了多种结构元素创建方法。

#### 问：如何使用PDF文档保存带标签的PDF文档？`Save` method ensure the preservation of structure elements?

答： 的`Save`方法将 PDF 文档与创建的结构元素一起保存，确保保留文档的层次结构和语义结构，以便于访问和导航。

#### 问：结构元素在辅助技术的可访问性和兼容性方面为 PDF 文档带来了哪些好处？

答：结构元素通过为文档提供有意义的结构和语义来增强可访问性。这使得屏幕阅读器等辅助技术能够更有效地向残障用户解释和传达文档内容。

#### 问：如何在 PDF 文档中进一步自定义和组合不同类型的结构元素？

答：您可以使用Aspose.PDF提供的适当的创建方法来组合和自定义结构元素。尝试不同的元素及其属性，以创建结构良好且组织良好的 PDF 文档。