---
title: Create Note Structure Element
linktitle: Create Note Structure Element
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to create structured note items in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 30
url: /ru/net/programming-with-tagged-pdf/create-note-structure-element/
---
In this tutorial, we will provide you with a step-by-step guide on how to create a note structure element in a PDF document using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows you to create, manipulate and convert PDF documents programmatically. Using the marked content structure features of Aspose.PDF, you can add structured notes to your PDF document.

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

## Step 3: Creating the PDF Document and Note Structured Elements

Use the following code to create a PDF document and add note structured elements:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

This code creates an empty PDF document and adds structured note elements to a paragraph. Each note is created using the methods provided by Aspose.PDF.

## Step 4: Saving the PDF Document

Use the following code to save the PDF document:

```csharp
document. Save(outFile);
```

This code saves the PDF document with the note structured elements to a specified file.

### Sample source code for Create Note Structure Element using Aspose.PDF for .NET 

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Create Pdf Document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Add Paragraph Element
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Add NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Add NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Add NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Must throw exception - Aspose.Pdf.Tagged.TaggedException : Structure element with ID='note_002' already exists
//note3.SetId("note_002");
// Resultant document does not compliance to PDF/UA If ClearId() used for Note Structure Element
//note3.ClearId();
// Save Tagged Pdf Document
document.Save(outFile);
// Checking PDF/UA compliance
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

In this tutorial, you learned how to create note structure elements in a PDF document using Aspose.PDF for .NET. Structured note elements allow you to add additional, structured information to your PDF document.

### FAQ's

#### Q: What is the purpose of creating note structure elements in a PDF document using Aspose.PDF for .NET?

A: Creating note structure elements in a PDF document using Aspose.PDF for .NET allows you to add structured notes to the document's content. These notes can provide additional context, explanations, or references to specific parts of the content.

#### Q: How does the Aspose.PDF library assist in creating note structure elements in a PDF document?

A: Aspose.PDF for .NET is a powerful library that provides functionalities for creating, manipulating, and converting PDF documents programmatically. In this tutorial, the library's marked content structure features are used to create structured note elements within the PDF document's content.

#### Q: What are the prerequisites for creating note structure elements in a PDF document using Aspose.PDF for .NET?

A: Before you begin, ensure that you have Visual Studio installed with the .NET framework and have the Aspose.PDF library for .NET referenced in your project.

#### Q: How does the provided C# code create note structure elements in the PDF document's content?

A: The code demonstrates how to create a PDF document, define note structured elements, and add them to a paragraph. Each note is created using methods provided by Aspose.PDF, allowing you to incorporate structured notes into the content.

#### Q: Can I customize the content and properties of the note structure elements I create?

A: Yes, you can customize the content and properties of note structure elements by using the methods and properties provided by the Aspose.PDF library. The code showcases how to set the text and ID of note elements, but you can further customize them as needed.

#### Q: How is the hierarchical relationship established between the note structure elements and the document's content?

A: The hierarchical relationship is established by adding note structure elements as children of other structured elements, such as paragraphs. In the code, note elements are appended to a paragraph element using the `AppendChild` method.

#### Q: Can I assign unique IDs to note structure elements?

A: Yes, you can assign unique IDs to note structure elements using the `SetId` method. The code demonstrates how to set the IDs of note elements to unique values.

#### Q: What happens if I attempt to assign a duplicate ID to a note structure element?

A: Attempting to assign a duplicate ID to a note structure element will result in an exception. The code provided in the tutorial includes a comment illustrating this scenario.

#### Q: How can I ensure PDF/UA compliance when creating note structure elements?

A: The code provided in the tutorial demonstrates how to validate PDF/UA compliance using the `Validate` method. By validating the document against the PDF/UA standard, you can ensure that the added note structure elements adhere to accessibility guidelines.

#### Q: Can I use this approach to add note structure elements to an existing PDF document?

A: Yes, you can modify the provided approach to add note structure elements to an existing PDF document. Instead of creating a new document, you would load the existing document using Aspose.PDF and then follow similar steps to append note elements.
