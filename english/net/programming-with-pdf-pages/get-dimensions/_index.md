---
title: Get Dimensions
linktitle: Get Dimensions
second_title: Aspose.PDF for .NET API Reference
description: In this tutorial, we explain how to get PDF page dimensions and perform manipulations using Aspose.PDF for .NET. Detailed steps are provided to guide you through the process.
type: docs
weight: 60
url: /pdf/net/programming-with-pdf-pages/get-dimensions/
---
In this tutorial, we'll walk you through the step-by-step process of getting page dimensions in a PDF file using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to get the dimensions of a page in a PDF file using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where your PDF file is located. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Then you can open the PDF file using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Step 3: Add a blank page (if needed)
If the PDF document already contains pages, you can jump to an existing page using the index `1` (the first page has an index of 1). Otherwise, you can add a new page to the document.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Step 4: Get page dimensions
You can now get the page dimensions using the `GetPageRect()` method of the `Page` object. This method returns a `Rectangle` object containing the dimensions of the page. You can access the width and height using the `Width` and `Height` properties.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Step 5: Rotate the page
If you want to rotate the page, you can use the `Rotate` property of the `Page` object. In this example, the page is rotated 90 degrees.

```csharp
page. Rotate = Rotate. on90;
```

## Step 6: Get page dimensions again
After page rotation, you can get the page dimensions again using the `GetPageRect()` method.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Sample source code for Get Dimensions using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Adds a blank page to pdf document
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Get page height and width information
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Rotate page at 90 degree angle
page.Rotate = Rotation.on90;
// Get page height and width information
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusion
In this tutorial, we learned how to get the dimensions of a page in a PDF file using Aspose.PDF for .NET. By following the steps provided, you can easily extract page dimensions and perform other PDF manipulation operations. Aspose.PDF for .NET offers great flexibility for working with PDF files and allows you to develop powerful and customized solutions.

Feel free to further explore the documentation of Aspose.PDF to discover all the features offered by this library.

