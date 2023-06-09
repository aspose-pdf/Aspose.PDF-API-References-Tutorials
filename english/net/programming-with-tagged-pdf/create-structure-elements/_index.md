---
title: Create Structure Elements
linktitle: Create Structure Elements
second_title: Aspose.PDF for .NET API Reference
description: In this tutorial, you will learn how to use Aspose.PDF for .NET to create structural elements in a tagged PDF document.
type: docs
weight: 60
url: /net/programming-with-tagged-pdf/create-structure-elements/
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

