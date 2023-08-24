---
title: Custom Tag Name
linktitle: Custom Tag Name
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to using a custom tag name with Aspose.PDF for .NET. Improve the structure of your PDFs with custom tags.
type: docs
weight: 90
url: /ar/net/programming-with-tagged-pdf/custom-tag-name/
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

### FAQ's

#### Q: What is a custom tag name in the context of PDF documents, and why would I use it with Aspose.PDF for .NET?

A: A custom tag name in a PDF document is a user-defined label that provides specific structural information to the document's content. Using custom tag names with Aspose.PDF for .NET allows you to enhance the accessibility and organization of the PDF document, making it easier to navigate, understand, and interact with.

#### Q: How does Aspose.PDF for .NET facilitate the use of custom tag names in PDF documents?

A: Aspose.PDF for .NET provides a set of classes and methods that enable you to create, manipulate, and assign custom tag names to different structural elements within a PDF document. This helps you add semantic meaning and context to the document's content.

#### Q: What role does the `taggedContent` object play in using custom tag names?

A: The `taggedContent` object, obtained from the document's `TaggedContent` property, allows you to work with structured elements in the PDF document. You can create, organize, and assign custom tag names to these elements, enhancing the document's semantic structure.

#### Q: How do custom tag names improve document accessibility and usability?

A: Custom tag names provide additional context and semantics to the document's content, which improves its accessibility for assistive technologies and enhances the overall user experience. Screen readers and other assistive devices can use custom tag names to convey meaningful information to users.

#### Q: Can I use custom tag names for various types of structural elements in a PDF document?

A: Yes, you can assign custom tag names to a wide range of structural elements, including paragraphs, spans, sections, and more. This allows you to categorize and label different parts of the document's content, creating a more organized and understandable layout.

#### Q: How do I define and assign custom tag names to elements in a PDF document using Aspose.PDF for .NET?

A: You can define and assign custom tag names by creating logical structure elements, such as paragraphs and spans, and then using the `SetTag` method to assign the desired custom tag name to these elements. The provided code example demonstrates this process.

#### Q: How do I ensure that the custom tag names I use are compatible with accessibility standards and best practices?

A: When choosing custom tag names, it's recommended to follow accessibility guidelines and use descriptive and meaningful labels that accurately represent the content. Consulting relevant accessibility standards and documentation can help you select appropriate custom tag names.

#### Q: Can I combine the use of custom tag names with other PDF manipulation features offered by Aspose.PDF for .NET?

A: Absolutely! You can combine the use of custom tag names with other features of Aspose.PDF for .NET, such as creating tables, adding images, inserting hyperlinks, and more. This allows you to create rich and accessible PDF documents with structured content.

#### Q: How can I validate the effectiveness of using custom tag names for accessibility and usability in my PDF documents?

A: You can validate the effectiveness of custom tag names by using assistive technologies like screen readers to navigate and interact with the PDF document. Additionally, you can test the document's compliance with accessibility standards and guidelines using tools and validators.

#### Q: How can I extend this knowledge to create more complex document structures and utilize custom tag names for advanced scenarios?

A: You can extend this knowledge by exploring additional features of Aspose.PDF for .NET, such as creating nested structure elements, using custom tags for form fields, incorporating multimedia elements, and more. The library's documentation and examples provide guidance for these advanced scenarios.