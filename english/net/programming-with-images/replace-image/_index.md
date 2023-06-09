---
title: Replace Image
linktitle: Replace Image
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to replacing an image in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 240
url: /net/programming-with-images/replace-image/
---

In this tutorial, we'll walk you through how to replace an image in a PDF document using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## Step 1: Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## Step 2: Loading the PDF document

To get started, use the following code to load the PDF document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open the document
Document pdfDocument = new Document(dataDir + "ReplaceImage.pdf");
```

Be sure to provide the correct path to your PDF document.

## Step 3: Replacement of a specific image

To replace a specific image in the PDF document, use the following code:

```csharp
// Replace a specific image
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
```

In this example, we replace the image located on page 1 of the PDF document. Be sure to provide the correct path to the new image you want to use.

## Step 4: Saving the updated PDF file

After performing the image replacement, save the updated PDF file using the following code:

```csharp
dataDir = dataDir + "ReplaceImage_out.pdf";
// Save the updated PDF file
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved as: " + dataDir);
```

Be sure to provide the desired path and filename for the updated PDF file.

### Sample source code for Replace Image using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "ReplaceImage.pdf");
// Replace a particular image
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
dataDir = dataDir + "ReplaceImage_out.pdf";
// Save updated PDF file
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Congratulation ! You have successfully replaced an image in a PDF document using Aspose.PDF for .NET. Now you can apply this method to your own projects to edit images in PDF files.
