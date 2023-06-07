---
title: Create Structure Elements Tree
linktitle: Create Structure Elements Tree
second_title: Aspose.PDF for .NET API Reference
description: Create a structure of tree elements using Aspose.PDF for .NET. Step by step guide to create a structured PDF document.
type: docs
weight: 70
url: /net/programming-with-tagged-pdf/create-structure-elements-tree/
---
In this step-by-step guide, we will explain the source code in C# to create a structure of tree elements using Aspose.PDF for .NET. We will show you how to create a PDF document with structured elements and how to organize them hierarchically. Using the Aspose.PDF library greatly simplifies the manipulation of PDF elements and provides advanced functionality for working with structured documents.

## Step 1: Setting up the environment
Before you begin, make sure you've set up your development environment with Aspose.PDF for .NET. Also make sure you have the path to your documents directory set in the `dataDir` variable.

## Step 2: Creating a PDF Document
To start, we'll create a new PDF document using the `Document` class provided by Aspose.PDF. Here is the code for this step:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a PDF document
Document document = new Document();
```

## Step 3: Getting content to work with TaggedPdf
The Aspose.PDF library allows working with structured PDF documents using the concept of Tagged PDF. For this, we need to get a reference to the tagged content item using the document's `TaggedContent` property. Here is the code for this step:

```csharp
// Get content to work with TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## Step 4: Set document title and language
Before we start creating the structure of the elements, we need to define the title and the language of the document. This can be done using the `SetTitle` and `SetLanguage` methods of the `taggedContent` object. Here is the code for this step:

```csharp
// Define the document title and language
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## Step 5: Creating Logical Structure Elements
Now that we've set up our document and set the title and language, we can start creating logical structure elements. These elements will be organized hierarchically to form the structure tree. Here is the code for this step:

```csharp
// Obtain the root structure element (Document)
StructureElement rootElement = taggedContent.RootElement;

// Create the logical structure
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## Step 6: Saving the tagged PDF document
Once we have created the element structure, we can save the PDF document. Use the `Save` method of the `document` object to specify the path and name of the PDF file to save. Here is the code for this step:

```csharp
// Save the tagged PDF document
document.Save(dataDir + "StructureElementsTree.pdf");
```

### Sample source code for Create Structure Elements Tree using Aspose.PDF for .NET 
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
// Get root structure element (Document)
StructureElement rootElement = taggedContent.RootElement;
// Create Logical Structure
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
// Save Tagged Pdf Document
document.Save(dataDir + "StructureElementsTree.pdf");

```

## Conclusion
You have learned how to create a structure of tree elements using Aspose.PDF for .NET. This guide has shown you the steps needed to set up a PDF document, create logical structure elements, and save the final document. By using Aspose.PDF, you can easily manipulate PDF elements and create structured documents.

