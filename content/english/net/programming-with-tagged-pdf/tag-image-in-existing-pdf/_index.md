---
title: Tag Image In Existing PDF
linktitle: Tag Image In Existing PDF
second_title: Aspose.PDF for .NET API Reference
description: Learn how to tag images in existing PDFs using Aspose.PDF for .NET. Step-by-step guide to enhance accessibility with PDF/UA compliance.
type: docs
weight: 210
url: /net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Introduction

In this tutorial, we’ll walk you through how to tag an image in an existing PDF using Aspose.PDF for .NET. By the end of this guide, you’ll be able to set alternative text for images, adjust layout attributes, and ensure your PDF complies with accessibility standards.

## Prerequisites

Before we dive in, let's go over what you'll need to get started:

- Aspose.PDF for .NET: Make sure you’ve downloaded and installed the latest version of Aspose.PDF for .NET. [Download here](https://releases.aspose.com/pdf/net/).
- .NET Framework: Ensure that you have a .NET development environment like Visual Studio set up.
- Basic Understanding of PDF Structure: Familiarity with PDF structure elements such as paragraphs, spans, tables, and images.
- A Valid License: You can either buy a license [here](https://purchase.aspose.com/buy) or use a temporary one [here](https://purchase.aspose.com/temporary-license/).

## Import Packages

To begin coding, you need to import the essential namespaces from Aspose.PDF for .NET. These will give you access to the necessary classes and methods to manipulate the PDF document.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Now that we’ve set the stage, let’s break down the process of tagging an image into multiple steps.

## Step 1: Load the Existing PDF Document

The first step is to load the PDF file that you want to work with. This can be any PDF file with an image that you wish to tag.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Open the document
Document document = new Document(inFile);
```

- Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your file.
- The `Document` class allows you to load an existing PDF. You’ll be modifying this PDF to tag the image.

## Step 2: Access Tagged Content and Root Structure Element

Once you’ve opened the PDF, the next step is to access the tagged content and identify the root structure element. This is crucial as it allows you to navigate through the elements in the PDF and make modifications.

```csharp
// Get tagged content and root structure element
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` provides access to the structured elements in the PDF.
- The `RootElement` is the topmost structure element, from which you can traverse down to other elements like paragraphs, tables, and images.

## Step 3: Set the Title for the Tagged PDF Document

Adding a title to the tagged PDF document ensures that your document is properly labeled, which is helpful for accessibility and PDF/UA compliance.

```csharp
// Set title for the tagged PDF document
taggedContent.SetTitle("Document with images");
```

- Setting a title for your tagged PDF enhances accessibility and improves document clarity for screen readers and assistive technologies.

## Step 4: Find and Tag the Image

Now, let’s find the image element (referred to as a `FigureElement` in Aspose.PDF), set an alternative text for it, and configure its layout attributes.

```csharp
// Loop through all Figure elements (images) and set alternative text and layout attributes
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Set alternative text for the figure
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Create and set BBox attribute (bounding box)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Set layout attributes for the figure
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

- This code loops through all the `FigureElement` objects in the root structure, which represent images.
- It sets the alternative text for accessibility (screen readers will use this to describe the image).
- The bounding box (`BBox`) specifies the coordinates for the image's layout, ensuring it’s correctly displayed in the document.

## Step 5: Modify Span Elements within the Table

In some cases, you may need to modify span elements within a table. Here, we’ll demonstrate how to find a `SpanElement` and move it into a paragraph.

```csharp
// Find the table, span, and paragraph elements
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Move the span element into the paragraph
spanElement.ChangeParentElement(paragraph);
```

- Here, we locate the `TableElement`, `SpanElement`, and `ParagraphElement` within the PDF.
- Using the `ChangeParentElement` method, we move the span into the paragraph to ensure proper tagging and structure.

## Step 6: Save the Document and Validate PDF/UA Compliance

Once all the changes are made, the final step is to save the updated PDF and check whether it complies with PDF/UA standards.

```csharp
// Save the updated PDF document
document.Save(outFile);

// Validate PDF/UA compliance
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

- The `Validate` method checks the PDF document against PDF/UA standards and logs the results.
- Ensuring compliance helps improve accessibility and meet regulatory requirements for document publishing.

## Conclusion

In this tutorial, we’ve shown you how to tag images in an existing PDF using Aspose.PDF for .NET. By setting alternative text, adjusting layout attributes, and validating the document for PDF/UA compliance, you can ensure that your PDFs are accessible and meet modern standards. Aspose.PDF makes it easy to work with structured elements, giving you control over your document's layout and accessibility.

## FAQ's

### What is Aspose.PDF for .NET used for?
Aspose.PDF for .NET is a powerful library used for creating, editing, and manipulating PDF documents programmatically in a .NET environment.

### How do I ensure PDF/UA compliance?
You can use Aspose.PDF’s `Validate` method to check for PDF/UA compliance after making modifications to the document.

### What is alternative text in PDFs?
Alternative text is a description added to images in PDFs to improve accessibility, especially for users relying on screen readers.

### Can I manipulate tables and spans in a PDF with Aspose.PDF?
Yes, Aspose.PDF allows you to manipulate tables, spans, and other structured elements within a PDF document.

### Where can I download Aspose.PDF for .NET?
You can download the latest version of Aspose.PDF for .NET [here](https://releases.aspose.com/pdf/net/).
