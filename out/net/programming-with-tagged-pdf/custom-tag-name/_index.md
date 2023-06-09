---
title: Custom Tag Name
linktitle: Custom Tag Name
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to using a custom tag name with Aspose.PDF for .NET. Improve the structure of your PDFs with custom tags.
type: docs
weight: 90
url: /content/net/programming-with-tagged-pdf/custom-tag-name/
---
In this step-by-step guide, we'll walk you through how to use a custom tag name with Aspose.PDF for .NET. Aspose.PDF is a powerful library that lets you manipulate PDF documents programmatically. Using custom tags allows you to add specific structural information to your PDF document, making it easier to use and easier to access.

Let's dive into the code and learn how to use a custom tag name with Aspose.PDF for .NET.

## Prerequisites

Before you begin, make sure you have the following:

1. Aspose.PDF library for .NET installed.
2. A basic knowledge of the C# programming language.

## Step 1: Setting up the environment

To get started, open your C# development environment and create a new project. Make sure you have added a reference to the Aspose.PDF library for .NET in your project.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the document

The first step is to create a new PDF document using the `Document` class.

```csharp
// Create the PDF document
Document document = new Document();
```

## Step 3: Work with tagged content

Then we get the tagged content of the document to work with.

```csharp
// Get the tagged content of the document
ITaggedContent taggedContent = document.TaggedContent;
```

## Step 4: Set document title and language

We can now set the document title and language.

```csharp
// Define the document title and language
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Step 5: Create Logical Structure Elements

Now let's create some logical structure elements to organize our content.

```csharp
// Create logical structure elements
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Here we create paragraph elements and span elements for our content, and assign custom tags to them.

## Step 6: Save the tagged PDF document

Finally, we save the tagged PDF document.

```csharp
// Save the tagged PDF document
document.Save(dataDir + "CustomTag.pdf");
```

### Sample source code for Custom Tag Name using Aspose.PDF for .NET 
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

// Create Logical Structure Elements
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Save Tagged Pdf Document
document.Save(dataDir + "CustomTag.pdf");

```

## Conclusion

Congratulation ! You have learned how to use a custom tag name with Aspose.PDF for .NET. You can now add specific structural information to your PDF document using custom tags. Explore more features of Aspose.PDF to discover its full potential.
