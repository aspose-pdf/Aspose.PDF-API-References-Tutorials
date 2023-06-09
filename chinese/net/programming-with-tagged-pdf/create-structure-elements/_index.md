---
title: 创建结构元素
linktitle: 创建结构元素
second_title: Aspose.PDF for .NET API 参考
description: 在本教程中，您将学习如何使用 Aspose.PDF for .NET 在带标签的 PDF 文档中创建结构元素。
type: docs
weight: 60
url: /zh/net/programming-with-tagged-pdf/create-structure-elements/
---
以下 C# 源代码使用 Aspose.PDF for .NET 创建结构元素。请按照以下步骤了解代码的工作原理。

## 第一步：导入必要的库

```csharp
using Aspose.Pdf;
```

## 第 2 步：定义文档的目录

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必指定文档目录的正确路径。

## 第 3 步：创建 PDF 文档

```csharp
Document document = new Document();
```

我们创建一个代表 PDF 文档的新 Document 对象。

## 第 4 步：获取内容以使用 TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

我们检索 PDF 文档的标记内容。这将使我们能够操纵结构元素。

## 第 5 步：设置文档标题和语言

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

我们设置标记的 PDF 文档的标题和语言。这提高了文档的可访问性。

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

## 步骤 8：创建内联层次结构元素

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

我们为出现在段落或标题内的文本部分创建内联层次结构元素。

## 第 9 步：创建图稿结构元素

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

我们为文档中的插图和数学公式创建结构元素。

## 第 10 步：保存标记的 PDF 文档

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

我们使用创建的结构元素保存标记的 PDF 文档。

### 使用 Aspose.PDF for .NET 创建结构元素的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 PDF 文档
Document document = new Document();
//使用 TaggedPdf 获取内容
ITaggedContent taggedContent = document.TaggedContent;
//为 Documnet 设置标题和语言
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
//保存标记的 Pdf 文档
document.Save(dataDir + "StructureElements.pdf");

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在带标签的 PDF 文档中创建结构元素。结构元素有助于提高文档的可访问性并以有意义的方式组织内容。现在您可以使用这些知识来创建结构化、易于浏览的 PDF 文档。
