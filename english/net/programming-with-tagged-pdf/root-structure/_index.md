---
title: Root Structure
linktitle: Root Structure
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to using root structure elements with Aspose.PDF for .NET to access the root and StructTreeRoot object of the PDF document.
type: docs
weight: 130
url: /net/programming-with-tagged-pdf/root-structure/
---
In this step-by-step guide, we are going to show you how to use root structure elements with Aspose.PDF for .NET. Aspose.PDF is a powerful library that lets you create and manipulate PDF documents programmatically. Root structure elements allow you to access the StructTreeRoot object of the PDF document and the root structure element.

Let's dive into the code and learn how to use root structure elements with Aspose.PDF for .NET.

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

## Step 5: Access the root structure element

Now we can access the document's StructTreeRoot object and root structure element.

```csharp
// Access the root structure element
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;
```

### Sample source code for Root Structure using Aspose.PDF for .NET 
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

// Properties StructTreeRootElement and RootElement are used for access to 
// StructTreeRoot object of pdf document and to root structure element (Document structure element).
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;

```

## Conclusion

Congratulation ! You have learned how to use root structure elements with Aspose.PDF for .NET. You can now access the PDF document's StructTreeRoot object and root structure element to perform advanced operations on the document structure.

