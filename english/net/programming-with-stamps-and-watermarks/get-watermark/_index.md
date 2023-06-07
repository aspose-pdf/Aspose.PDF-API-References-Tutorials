---
title: Get Watermark
linktitle: Get Watermark
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract watermarks from your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 100
url: /net/programming-with-stamps-and-watermarks/get-watermark/
---
In this tutorial, we will take you step by step on how to get a watermark from a PDF document using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to iterate through the artifacts of a specific page and get the watermark type, text, and location.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Getting the watermark

Now that you have loaded the PDF document, you can iterate through the specific page artifacts to get the watermark information. Here's how:

```csharp
// Browse artifacts and get watermark subtype, text and location
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

The above code loops through all artifacts on the first page of the PDF document and displays the subtype, text, and rectangle (location) of each watermark encountered.

### Sample source code for Get Watermark using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Iterate through and get tub-type, text and location of artifact
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Conclusion

Congratulation ! You have learned how to get watermark information from a PDF document using Aspose.PDF for .NET. Now you can use this knowledge to analyze and process watermarks in your PDF documents.

