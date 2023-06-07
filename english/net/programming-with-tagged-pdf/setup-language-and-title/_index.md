---
title: Setup Language And Title
linktitle: Setup Language And Title
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to configure the language and title of a PDF document with Aspose.PDF for .NET. Create personalized multilingual documents.
type: docs
weight: 140
url: /net/programming-with-tagged-pdf/setup-language-and-title/
---
In this guide, we are going to tell you how to configure the language and title of a PDF document using the Aspose.PDF library for .NET. Aspose.PDF is a powerful library that lets you programmatically create, manipulate, and convert PDF files.

Let's dive into the code and learn how to configure the language and title of a PDF document using Aspose.PDF for .NET.

## Prerequisites

Before you start, make sure you have installed Aspose.PDF for .NET and set up your development environment.

## Step 1: Creating the document

The first step is to create a new PDF document using the `Document` class.

```csharp
// Create the PDF document
Document document = new Document();
```

## Step 2: Access tagged content

Next, we access the tagged content of the document using the `ITaggedContent` object.

```csharp
// Access tagged content
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Step 3: Set title and language

Now we can set the document title and language using the `SetTitle` and `SetLanguage` methods of the `ITaggedContent` object.

```csharp
// Define the title of the document
taggedContent.SetTitle("Example of tagged document");

// Set the document language
taggedContent.SetLanguage("fr-FR");
```

## Step 4: Add multilingual content

Next, we add multilingual content to the document using paragraph elements for each language.

```csharp
// Add a paragraph in English
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Add a paragraph in German
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Add a paragraph in French
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Add a paragraph in Spanish
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Step 5: Save the tagged PDF document

Finally, we save the tagged PDF document.

```csharp
// Save the tagged PDF document
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Sample source code for Setup Language And Title using Aspose.PDF for .NET 
```csharp

Document document = new Document();

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Get TaggedContent
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Set Title and Language
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Header (en-US, inherited from document)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Paragraph (English)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Paragraph (German)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Paragraph (French)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Paragraph (Spanish)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Save Tagged Pdf Document
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Conclusion

Congratulation ! You now know how to configure the language and title of a PDF document using Aspose.PDF for .NET. You can further explore the features of Aspose.PDF to create personalized and multilingual PDF documents.

