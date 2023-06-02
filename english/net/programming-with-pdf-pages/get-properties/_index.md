---
title: Get Properties
linktitle: Get Properties
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to get PDF properties like box dimensions and rotation using Aspose.PDF for .NET.
type: docs
weight: 100
url: /net/programming-with-pdf-pages/get-properties/
---

In this tutorial, we'll walk you through the step-by-step process to get the properties of a PDF using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to access different properties of a PDF page such as art box, crop box, crop box, etc., using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Set document directory
First, you need to set the path to your documents directory. This is the location of the PDF file whose properties you want to get. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Next, you need to open the PDF document using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Step 3: Access the Page Collection
Now you can access the document's pages collection using the `Pages` property of the `pdfDocument` object.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Step 4: Go to a specific page
Then you can jump to a specific page using the index of the page in the collection. In the example below, we access the second page (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Step 5: Get page properties
Now you can get the different properties of the PDF page, such as art box, crop box, crop box, etc., by using the corresponding properties of the `pdfPage` object.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Sample source code for Get Properties using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Get page collection
PageCollection pageCollection = pdfDocument.Pages;
// Get particular page
Page pdfPage = pageCollection[1];
// Get page properties
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Conclusion
Congratulation ! You have successfully obtained the properties of a PDF using Aspose.PDF for .NET. You learned how to open a PDF document, navigate to a specific page, and get various page properties, such as dimension boxes and rotation. You can now use this information to customize the handling of your PDF files based on their properties.

Be sure to check out the official Aspose.PDF for .NET documentation for more information on advanced features and customization possibilities.

