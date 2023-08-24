---
title: Get PDF Properties
linktitle: Get PDF Properties
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to get PDF properties like box dimensions and rotation using Aspose.PDF for .NET.
type: docs
weight: 100
url: /ru/net/programming-with-pdf-pages/get-properties/
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

### FAQ's

#### Q: How can I get the properties of a PDF using Aspose.PDF for .NET?

A: To get the properties of a PDF using Aspose.PDF for .NET, you can follow these steps:

1. Set the document directory by specifying the path to the PDF file whose properties you want to retrieve.
2. Open the PDF document using the `Document` class of Aspose.PDF, providing the correct path to the PDF file.
3. Access the document's pages collection using the `Pages` property of the `pdfDocument` object.
4. Jump to a specific page using the index of the page in the collection (indexing starts from 1).
5. Get the different properties of the PDF page, such as ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number, and Rotation, by using the corresponding properties of the `pdfPage` object.

#### Q: What are the different properties of a PDF page that I can retrieve using Aspose.PDF for .NET?

A: You can retrieve various properties of a PDF page using Aspose.PDF for .NET, such as:

- ArtBox: Represents the dimensions of the page's artwork.
- BleedBox: Represents the dimensions of the page's bleed.
- CropBox: Represents the dimensions of the page's visible content after cropping.
- MediaBox: Represents the dimensions of the page's physical media.
- TrimBox: Represents the dimensions of the page's trimmed content.
- Rect: Represents the dimensions of the page's bounding box.
- Page Number: Represents the page number in the document.
- Rotate: Represents the rotation angle of the page.

#### Q: How do I access a specific page in the PDF document to retrieve its properties?

A: To access a specific page in the PDF document and retrieve its properties, you can use the `Pages` property of the `pdfDocument` object to access the document's pages collection. Then, you can use the index of the page in the collection to jump to the desired page. For example, to access the second page, you can use `pdfDocument.Pages[1]` (indexing starts from 1).

#### Q: Can I perform operations on the retrieved properties, such as modifying or resizing the page boxes?

A: Yes, once you retrieve the properties of a PDF page using Aspose.PDF for .NET, you can perform various operations on them. For example, you can modify the dimensions of the page boxes, rotate the page, or use the retrieved information for custom processing and manipulation of the PDF document.

#### Q: Does Aspose.PDF for .NET support extracting properties from encrypted or password-protected PDF files?

A: Yes, Aspose.PDF for .NET supports extracting properties from encrypted or password-protected PDF files. As long as you provide the correct password to open the PDF document, you can access and retrieve its properties using the same approach demonstrated in the tutorial.