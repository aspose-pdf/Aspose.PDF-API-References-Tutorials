---
title: Create Note Structure Element
linktitle: Create Note Structure Element
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to create structured note items in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 30
url: /content/net/programming-with-tagged-pdf/create-note-structure-element/
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
