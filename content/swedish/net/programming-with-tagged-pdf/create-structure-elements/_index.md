---
title: Create Structure Elements
linktitle: Create Structure Elements
second_title: Aspose.PDF for .NET API Reference
description: In this tutorial, you will learn how to use Aspose.PDF for .NET to create structural elements in a tagged PDF document.
type: docs
weight: 60
url: /sv/net/programming-with-tagged-pdf/create-structure-elements/
---
The following C# source code uses Aspose.PDF for .NET to create structure elements. Follow the steps below to understand how the code works.

## Step 1: Import the necessary libraries

```csharp
using Aspose.Pdf;
```

## Step 2: Define the directory of your documents

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to specify the correct path to your documents directory.

## Step 3: Create a PDF document

```csharp
Document document = new Document();
```

We create a new Document object that represents the PDF document.

## Step 4: Get content to work with TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

We retrieve the tagged content of the PDF document. This will allow us to manipulate structural elements.

## Step 5: Set document title and language

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

We set the title and language of the tagged PDF document. This improves the accessibility of the document.

## Step 6: Create grouping elements

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

We create different structural elements for grouping content in the PDF document.

## Step 7: Create paragraph structure elements

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

We create block-level structural elements for paragraphs and headings. The example above shows the creation of a level 1 header.

## Step 8: Create inline level structure elements

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

We create inline level structure elements for the parts of text that appear inside a paragraph or heading.

## Step 9: Create artwork structure elements

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

We create structural elements for the illustrations and mathematical formulas present in the document.

## Step 10: Save the tagged PDF document

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

We save the tagged PDF document with the created structure elements.

### Sample source code for Create Structure Elements using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Pdf Document
Document document = new Document();
// Get Content for work with TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Set Title and Language for Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Create Grouping Elements
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
// Create Text Block-Level Structure Elements
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Create Text Inline-Level Structure Elements
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Create Illustration Structure Elements
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Methods are under development
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
// Save Tagged Pdf Document
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusion

In this tutorial, we learned how to use Aspose.PDF for .NET to create structure elements in a tagged PDF document. Structural elements help improve document accessibility and organize content in a meaningful way. Now you can use this knowledge to create structured, easy-to-navigate PDF documents.

### FAQ's

#### Q: What is the purpose of creating structure elements in a PDF document using Aspose.PDF for .NET?

A: Creating structure elements in a PDF document using Aspose.PDF for .NET enhances the accessibility and organization of the document's content. Structure elements provide a hierarchical structure that improves navigation, semantics, and compatibility with assistive technologies.

#### Q: How does the provided C# code create structure elements in a PDF document?

A: The code example demonstrates how to create various types of structure elements, including grouping elements (such as parts, sections, and divs), block-level elements (like paragraphs and headings), inline-level elements (span, quote, note), and artwork elements (such as figures and formulas). These structure elements help organize content.

#### Q: Why is it important to set the document's title and language using the `SetTitle` and `SetLanguage` methods?

A: Setting the document's title and language using the `SetTitle` and `SetLanguage` methods improves document accessibility and semantics. The title provides a brief description of the document's purpose, while the language attribute enhances language-specific rendering and accessibility.

#### Q: How do grouping elements, such as `PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Grouping elements create a hierarchical structure within the PDF document, allowing you to logically organize and group related content. This enhances navigation and provides a clear structure for users.

#### Q: What are block-level and inline-level structure elements, and how do they differ?

A: Block-level structure elements represent larger blocks of content, such as paragraphs and headings, while inline-level elements represent parts of text within a paragraph or heading, such as spans, quotes, and notes. They help define the hierarchy and relationships of content.

#### Q: How do artwork structure elements, like `FigureElement` and `FormulaElement`, contribute to the document?

A: Artwork structure elements allow you to add illustrations, figures, and mathematical formulas to the document. They provide a structured way to include visual and mathematical content.

#### Q: Can I use similar techniques to create other types of structure elements, like lists, tables, or annotations?

A: Yes, you can use similar techniques to create other types of structure elements like lists, tables, annotations, references, and more. Aspose.PDF provides a wide range of structure element creation methods.

#### Q: How does saving the tagged PDF document using the `Save` method ensure the preservation of structure elements?

A: The `Save` method saves the PDF document along with the created structure elements, ensuring that the document's hierarchical and semantic structure is preserved for accessibility and navigation.

#### Q: What benefits do structure elements bring to PDF documents in terms of accessibility and compatibility with assistive technologies?

A: Structure elements enhance accessibility by providing a meaningful structure and semantics to the document. This allows assistive technologies like screen readers to interpret and convey the document's content more effectively to users with disabilities.

#### Q: How can I further customize and combine different types of structure elements in my PDF documents?

A: You can combine and customize structure elements by using appropriate creation methods provided by Aspose.PDF. Experiment with different elements and their properties to create a well-structured and organized PDF document.