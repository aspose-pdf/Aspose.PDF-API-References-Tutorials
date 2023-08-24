---
title: Get Watermark From PDF File
linktitle: Get Watermark From PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract watermarks from PDF file with Aspose.PDF for .NET.
type: docs
weight: 100
url: /fr/net/programming-with-stamps-and-watermarks/get-watermark/
---
In this tutorial, we will take you step by step on how to get a watermark from PDF file using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to iterate through the artifacts of a specific page and get the watermark type, text, and location.

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

### FAQ's for get watermark from PDF file

#### Q: What is a watermark in a PDF document, and why would I need to extract its information?

A: A watermark in a PDF document is a recognizable image or text that is superimposed onto the content of the document, often to indicate its status, ownership, or confidential nature. Extracting watermark information can be useful for analyzing document authenticity, identifying document source, or processing documents based on watermark presence.

#### Q: How does the provided C# source code help in extracting watermark information from a PDF file?

A: The provided code demonstrates how to load an existing PDF document, iterate through the artifacts of a specific page, and extract information about watermarks. It does this by accessing the `Subtype`, `Text`, and `Rectangle` properties of each artifact.

#### Q: What does the `Subtype` property of an artifact represent?

A: The `Subtype` property of an artifact represents the type of the artifact. For watermarks, it indicates that the artifact is a watermark.

#### Q: How does the code determine the location (rectangle) of the watermark on the page?

A: The code uses the `Rectangle` property of the artifact to determine the location of the watermark. The `Rectangle` property represents the bounding rectangle of the artifact on the page.

#### Q: Can I modify the code to extract additional information about the watermark, such as its appearance or color?

A: Yes, you can modify the code to access other properties of the artifact, such as its appearance or color, if such information is available and relevant to your use case.

#### Q: Can I extract watermark information from multiple pages of a PDF document using this code?

A: Yes, you can modify the code to iterate through artifacts on multiple pages by changing the page index in the loop to access artifacts from different pages.

#### Q: What happens if there are no watermarks on the specified page?

A: If there are no watermarks on the specified page, the loop will not execute, and no watermark information will be displayed.

#### Q: How can I use the extracted watermark information for further processing?

A: The extracted watermark information can be used for various purposes, such as logging, analysis, reporting, or automation of specific actions based on the presence or properties of watermarks.

#### Q: Can I modify this code to extract information about other types of artifacts in a PDF document?

A: Yes, you can modify the code to extract information about other types of artifacts by accessing their properties using a similar approach.

#### Q: How can I access watermarks that are not artifacts but are part of the PDF content?

A: Watermarks that are not artifacts may be part of the PDF content itself, such as images or text. To extract information about these types of watermarks, you may need to analyze the PDF content and identify specific elements that represent the watermarks.