---
title: Add Structure Element Into Element
linktitle: Add Structure Element Into Element
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to add structure element to element in PDF document using Aspose.PDF for .NET.
type: docs
weight: 20
url: /sv/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
In this tutorial, we will provide you with a step-by-step guide on how to add a structure element to an element in a PDF document using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows you to create, manipulate and convert PDF documents programmatically. Using the marked content structure features of Aspose.PDF, you can create a hierarchical structure in your PDF document.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Visual Studio installed with .NET framework.
2. The Aspose.PDF library for .NET.

## Step 1: Project Setup

To get started, create a new project in Visual Studio and add a reference to the Aspose.PDF for .NET library. You can download the library from Aspose official website and install it on your machine.

## Step 2: Import the necessary namespaces

In your C# code file, import the namespaces required to access the classes and methods provided by Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Step 3: Creating the PDF document and defining the structured elements

Use the following code to create a PDF document and define the structured elements:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

This code creates an empty PDF document and adds structured elements such as paragraphs and spans. Each structure element is created using the methods provided by Aspose.PDF.

## Step 4: Saving the PDF Document

Use the following code to save the PDF document:

```csharp
document. Save(outFile);
```

This code saves the PDF document with the structured elements to a specified file.

### Sample source code for Add Structure Element Into Element using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Creation document and getting Tagged Pdf Content
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Setting Title and Nature Language for document
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Getting Root structure element (Document structure element)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Save Tagged Pdf Document
document.Save(outFile);
// Checking PDF/UA compliance
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

In this tutorial, you learned how to add a structure element to an element in a PDF document using Aspose.PDF for .NET. Using the marked content structure features of Aspose.PDF, you can create a hierarchical structure in your PDF document, which makes it easier to manage and navigate through content.

### FAQ's

#### Q: What is the purpose of adding a structure element to an element in a PDF document using Aspose.PDF for .NET?

A: Adding a structure element to an element in a PDF document using Aspose.PDF for .NET allows you to create a hierarchical structure within the document's content. This hierarchical structure enhances the organization and navigation of the content, making it easier to manage and access specific elements.

#### Q: How does the Aspose.PDF library assist in adding structure elements to a PDF document?

A: Aspose.PDF for .NET is a powerful library that provides capabilities for creating, manipulating, and converting PDF documents programmatically. In this tutorial, the library's marked content structure features are leveraged to create and append structure elements to the PDF document's content.

#### Q: What are the prerequisites for adding structure elements to a PDF document using Aspose.PDF for .NET?

A: Before you begin, ensure that you have Visual Studio installed with the .NET framework and have the Aspose.PDF library for .NET referenced in your project.

#### Q: How does the provided C# code create and append structure elements to the PDF document's content?

A: The code demonstrates how to create a PDF document, define a root structure element, and append various structured elements such as paragraphs and spans to it. Each structured element is created using methods provided by Aspose.PDF, allowing you to build a hierarchical structure.

#### Q: Can I customize the types of structure elements that I append to the PDF document?

A: Yes, you can customize the types of structure elements by exploring different methods provided by the Aspose.PDF library. The code showcases paragraphs and spans as examples, but you can create and append other types of structured elements as needed.

#### Q: How do I define the hierarchical relationship between the added structure elements?

A: The hierarchical relationship between structure elements is defined by the order in which you append them to their parent elements. In the code, the parent-child relationships are established by using the `AppendChild` method.

#### Q: What are the benefits of creating a hierarchical structure in a PDF document?

A: Creating a hierarchical structure in a PDF document enhances its accessibility, navigation, and organization. It allows assistive technologies to better interpret and convey the document's content, making it more user-friendly for individuals with disabilities.

#### Q: How can I validate PDF/UA compliance after adding structure elements?

A: The code provided in the tutorial demonstrates how to validate PDF/UA compliance using the `Validate` method. By validating the document against the PDF/UA standard, you can ensure that the added structure elements conform to accessibility guidelines.

#### Q: Can I use this approach to add structure elements to an existing PDF document?

A: Yes, you can modify the provided approach to add structure elements to an existing PDF document. Instead of creating a new document, you would load the existing document using Aspose.PDF and then follow similar steps to append structure elements.