---
title: 创建结构元素
linktitle: 创建结构元素
second_title: Aspose.PDF for .NET API 参考
description: 在本教程中，您将学习如何使用 Aspose.PDF for .NET 在标记的 PDF 文档中创建结构元素。
type: docs
weight: 60
url: /zh/net/programming-with-tagged-pdf/create-structure-elements/
---
以下 C# 源代码使用 Aspose.PDF for .NET 创建结构元素。按照以下步骤了解代码的工作原理。

## 步骤 1：导入必要的库

```csharp
using Aspose.Pdf;
```

## 第 2 步：定义文档目录

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请确保指定文档目录的正确路径。

## 步骤 3：创建 PDF 文档

```csharp
Document document = new Document();
```

我们创建一个代表 PDF 文档的新 Document 对象。

## 步骤 4：获取内容以使用 TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

我们检索 PDF 文档的标记内容。这将使我们能够操作结构元素。

## 步骤 5：设置文档标题和语言

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

我们设置了标记 PDF 文档的标题和语言。这提高了文档的可访问性。

## 步骤 6：创建分组元素

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

我们为段落和标题创建块级结构元素。上面的示例显示了如何创建 1 级标题。

## 步骤 8：创建内联级别结构元素

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

我们为段落或标题内出现的文本部分创建内联级别结构元素。

## 步骤 9：创建艺术品结构元素

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

我们为文档中的插图和数学公式创建结构元素。

## 步骤 10：保存标记的 PDF 文档

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

我们将标记的 PDF 文档与创建的结构元素一起保存。

### 使用 Aspose.PDF for .NET 创建结构元素的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 PDF 文档
Document document = new Document();
//获取使用 TaggedPdf 工作的内容
ITaggedContent taggedContent = document.TaggedContent;
//设置 Documnet 的标题和语言
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
//创建文本内联级结构元素
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
//保存带标签的 PDF 文档
document.Save(dataDir + "StructureElements.pdf");

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在带标签的 PDF 文档中创建结构元素。结构元素有助于提高文档可访问性并以有意义的方式组织内容。现在，您可以使用这些知识来创建结构化、易于导航的 PDF 文档。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 在 PDF 文档中创建结构元素的目的是什么？

答：使用 Aspose.PDF for .NET 在 PDF 文档中创建结构元素可增强文档内容的可访问性和组织性。结构元素提供层次结构，可改善导航、语义和与辅助技术的兼容性。

#### 问：提供的 C# 代码如何在 PDF 文档中创建结构元素？

答：代码示例演示了如何创建各种类型的结构元素，包括分组元素（例如部分、节和 div）、块级元素（例如段落和标题）、内联级元素（span、引文、注释）和插图元素（例如图片和公式）。这些结构元素有助于组织内容。

#### 问：为什么使用`SetTitle` and `SetLanguage` methods?

答：使用`SetTitle`和`SetLanguage`方法提高了文档的可访问性和语义。标题提供了文档目的的简要描述，而语言属性则增强了特定于语言的呈现和可访问性。

#### 问：如何对元素进行分组，例如`PartElement` and `SectElement`, contribute to the structure of the PDF document?

答：分组元素会在 PDF 文档中创建层次结构，让您可以有逻辑地组织和分组相关内容。这可以增强导航功能并为用户提供清晰的结构。

#### 问：什么是块级和内联级结构元素，它们有何不同？

答：块级结构元素表示较大的内容块，例如段落和标题，而内联级元素表示段落或标题内的文本部分，例如跨度、引文和注释。它们有助于定义内容的层次结构和关系。

#### 问：艺术品结构元素如何？`FigureElement` and `FormulaElement`, contribute to the document?

答：图稿结构元素允许您向文档添加插图、图形和数学公式。它们提供了一种包含视觉和数学内容的结构化方法。

#### 问：我可以使用类似的技术来创建其他类型的结构元素，如列表、表格或注释吗？

答：是的，您可以使用类似的技术创建其他类型的结构元素，如列表、表格、注释、引用等。Aspose.PDF 提供了多种结构元素创建方法。

#### 问：如何使用`Save` method ensure the preservation of structure elements?

答：`Save`方法将 PDF 文档与创建的结构元素一起保存，确保文档的层次和语义结构得以保留，以便于访问和导航。

#### 问：结构元素在可访问性和与辅助技术的兼容性方面为 PDF 文档带来哪些好处？

答：结构元素通过为文档提供有意义的结构和语义来增强可访问性。这允许屏幕阅读器等辅助技术更有效地解释和传达文档内容给残障用户。

#### 问：如何进一步自定义和组合 PDF 文档中不同类型的结构元素？

答：您可以使用 Aspose.PDF 提供的适当创建方法组合和自定义结构元素。尝试使用不同的元素及其属性来创建结构良好且组织有序的 PDF 文档。