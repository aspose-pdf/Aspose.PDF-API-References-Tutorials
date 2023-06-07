---
title: Counting Artifacts
linktitle: Counting Artifacts
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily count watermarks in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 60
url: /net/programming-with-stamps-and-watermarks/counting-artifacts/
---

In this tutorial, we will take you step by step on how to count artifacts in a PDF document using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to count the number of "watermark" artifacts on a specific page of the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the document
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Count artifacts

Now that you have loaded the PDF document, you can count the "watermark" type artifacts on a specific page of the document. Here's how:

```csharp
// Initialize the counter
int count = 0;

// Loop through all first page artifacts
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     // If the artifact subtype is "watermark", increment the counter
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

// Display the number of "watermark" type artifacts
Console.WriteLine("The page contains " + count + " watermarks");
```

The above code loops through all the artifacts on the first page of the PDF document and increments the counter for each "watermark" type artifact encountered.

### Sample source code for Counting Artifacts using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	// If artifact type is watermark, increate the counter
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## Conclusion

Congratulation ! You learned how to count "watermark" artifacts in a PDF document using Aspose.PDF for .NET. You can now use this knowledge to perform specific analysis and processing on artifacts in your PDF documents.

