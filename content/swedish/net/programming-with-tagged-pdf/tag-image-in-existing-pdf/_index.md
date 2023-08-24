---
title: Tag Image In Existing PDF
linktitle: Tag Image In Existing PDF
second_title: Aspose.PDF for .NET API Reference
description: Learn how to mark up an image in an existing PDF with Aspose.PDF for .NET. A Step-by-Step Guide to Adding Tags to Images.
type: docs
weight: 210
url: /sv/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In this detailed tutorial, we will walk you through the provided C# source code step by step to mark up an image in an existing PDF using Aspose.PDF for .NET. Follow the instructions below to understand how to add tags to an image in a PDF.

## Step 1: Setting up the environment

Before you begin, make sure you've configured your development environment to use Aspose.PDF for .NET. This includes installing the Aspose.PDF library and configuring your project to reference it.

## Step 2: Open the existing PDF document

In this step, we will open an existing PDF document using Aspose.PDF.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Input and output file paths
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Open the document
Document document = new Document(inFile);
```

We opened the existing PDF document using Aspose.PDF.

## Step 3: Obtain Tagged Content and Root Structure Element

Now we will get the tagged content of the PDF document and the corresponding root structure element.

```csharp
// Get tagged content and root structure element
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

We got the tagged content of the PDF document and the corresponding root structure element.

## Step 4: Setting the title for the tagged PDF document

Now let's set the title for the tagged PDF document.

```csharp
// Define the title for the tagged PDF document
taggedContent.SetTitle("Document with images");
```

We have set the title for the tagged PDF document.

## Step 5: Assign alt texts and bounding box to the image

Now, for each image element, we'll assign alt text and a bounding box.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Assign alternative text to the image
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Create and assign the bounding box (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

We've assigned alt text and a bounding box to each image element in the PDF document.

## Step 6: Moving the Span element into the paragraph

Now let's move the Span element into the paragraph.

```csharp
// Move Span element into paragraph (find incorrect span and paragraph in first TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Move the Span element in the paragraph
spanElement.ChangeParentElement(paragraph);
```

We moved the Span element into the specified paragraph.

## Step 7: Saving the modified PDF document

Now that we have made the necessary changes, we will save the modified PDF document.

```csharp
// Save the PDF document
document. Save(outFile);
```

We saved the modified PDF document in the specified directory.

### Sample source code for Tag Image In Existing PDF using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Open document
Document document = new Document(inFile);

// Gets tagged content and root structure element
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Set title for tagged pdf document
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Set Alternative Text  for Figure
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Create and Set BBox Attribute
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Move Span Element into Paragraph (find wrong span and paragraph in first TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Move Span Element into Paragraph
spanElement.ChangeParentElement(paragraph);

// Save document
document.Save(outFile);

// Checking PDF/UA Compliance for out document
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

In this tutorial, we learned how to mark up an image in an existing PDF using Aspose.PDF for .NET. You can now use Aspose.PDF to add tags and make edits to images in your PDF documents.

### FAQ's

#### Q: What is the main objective of this tutorial on tagging images in an existing PDF using Aspose.PDF for .NET?

A: The primary goal of this tutorial is to guide you through the process of marking up an image within an existing PDF document using Aspose.PDF for .NET. The tutorial provides step-by-step instructions and C# source code examples to help you understand how to assign alternative text and bounding boxes to images, move elements within the document, and add tags to images.

#### Q: What are the prerequisites for following this tutorial on tagging images in a PDF using Aspose.PDF for .NET?

A: Before you start, ensure that you have set up your development environment to use Aspose.PDF for .NET. This involves installing the Aspose.PDF library and configuring your project to reference it.

#### Q: How can I open an existing PDF document and access its tagged content using Aspose.PDF for .NET?

A: The tutorial provides C# source code examples that demonstrate how to open an existing PDF document using Aspose.PDF for .NET and access its tagged content for further manipulation.

#### Q: What is the purpose of assigning alternative text and bounding boxes to images in a PDF document?

A: Assigning alternative text and bounding boxes to images enhances accessibility by providing descriptive text for images and defining their layout and position within the document. This information is crucial for screen readers and other assistive technologies.

#### Q: How can I set the title for a tagged PDF document using Aspose.PDF for .NET?

A: The tutorial includes C# source code examples that illustrate how to set the title for a tagged PDF document using Aspose.PDF for .NET.

#### Q: What does the process of moving elements within a PDF document involve?

A: Moving elements within a PDF document involves changing the parent element of a particular element. In this tutorial, you'll learn how to move a Span element into a specified Paragraph element within a table.

#### Q: How do I save the modified PDF document after adding tags and making edits to images?

A: Once you've added tags, assigned alternative text, set bounding boxes, and made edits to the PDF document, you can use the provided C# source code examples to save the modified PDF document using the `Save()` method.

#### Q: What is the purpose of the sample source code provided in the tutorial?

A: The sample source code serves as a practical reference for implementing image tagging and manipulation using Aspose.PDF for .NET. You can use this code as a starting point and modify it to suit your specific requirements.

#### Q: Can I apply these techniques to other types of elements in a PDF document, not just images?

A: Yes, the techniques demonstrated in this tutorial can be adapted to work with various types of elements within a PDF document. You can apply similar principles to tag and manipulate other elements such as text, tables, and more.

#### Q: How can I validate the PDF/UA compliance of the modified PDF document?

A: The tutorial provides C# source code examples that show how to validate the PDF/UA compliance of the modified PDF document by using the `Validate()` method and generating an XML report.

#### Q: What other features does Aspose.PDF for .NET offer for working with PDF documents?

A: Aspose.PDF for .NET offers a wide range of features for working with PDF documents, including text manipulation, image insertion, table creation, form field management, digital signatures, annotations, and more. Consult the official documentation and resources for further exploration.