---
title: Text Structure Elements
linktitle: Text Structure Elements
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add text structure elements to a PDF document using Aspose.PDF for .NET. Improve the structure and accessibility of your PDFs.
type: docs
weight: 230
url: /net/programming-with-tagged-pdf/text-structure-elements/
---
In this detailed tutorial, we will walk you through the provided C# source code step by step to create text structure elements in a tagged PDF document using Aspose.PDF for .NET. Follow the instructions below to understand how to add text structure elements to your PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you've configured your development environment to use Aspose.PDF for .NET. This includes installing the Aspose.PDF library and configuring your project to reference it.

## Step 2: Creating the PDF document

In this step, we will create a new PDF document object with Aspose.PDF.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the PDF document
Document document = new Document();
```

We have created a new PDF document with Aspose.PDF.

## Step 3: Get tagged content and set title and language

Now let's get the tagged content of the PDF document and set the document title and language.

```csharp
// Get tagged content
ITaggedContent taggedContent = document.TaggedContent;

// Define the document title and language
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

We have set the title and language of the tagged PDF document.

## Step 4: Obtaining the root structure element

Now let's get the root structure element of the PDF document.

```csharp
// Obtain the root structure element
StructureElement rootElement = taggedContent.RootElement;
```

We have obtained the root structure element of the PDF document.

## Step 5: Adding the paragraph structure element

Now let's add a paragraph structure element to our PDF document.

```csharp
// Create the paragraph structure element
ParagraphElement p = taggedContent.CreateParagraphElement();

// Definition of the text of the paragraph structure element
p.SetText("Paragraph.");

// Add the paragraph structure element to the root structure element
rootElement.AppendChild(p);
```

We added a paragraph structure element with text to our PDF document.

## Step 6: Saving the PDF Document

Now that we're done editing the PDF document, let's save it to a file.

```csharp
// Save the tagged PDF document
document.Save(dataDir + "ElementDeStructureDeTexte.pdf");
```

We saved the PDF document tagged with the text structure element in the specified directory.


### Sample source code for Text Structure Elements using Aspose.PDF for .NET 

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

// Get Root Structure Elements
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p = taggedContent.CreateParagraphElement();

// Set Text to Text Structure Element
p.SetText("Paragraph.");
rootElement.AppendChild(p);

// Save Tagged Pdf Document
document.Save(dataDir + "TextStructureElement.pdf");
```

## Conclusion

In this tutorial, we learned how to use Aspose.PDF for .NET to add text structure elements to a PDF document. You can now use these features to improve the structure and accessibility of your PDF documents.