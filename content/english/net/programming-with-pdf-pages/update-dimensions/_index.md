---
title: Update PDF Page Dimensions
linktitle: Update PDF Page Dimensions
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to update PDF page dimensions using Aspose.PDF for .NET. Check the dimensions according to your needs.
type: docs
weight: 150
url: /net/programming-with-pdf-pages/update-dimensions/
---
In this tutorial, we'll walk you through the step-by-step process to update page dimensions in a PDF document using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to change page dimensions in a PDF document using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited PDF document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Then you can open the existing PDF document using the `Document` class of Aspose.PDF. Be sure to specify the correct document path.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Step 3: Get the Page Collection
Now you can access the pages collection of the PDF document using the `Pages` property of the `Document` class.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Step 4: Get a specific page
Then you can select a specific page of the document using the index of the page in the collection. In this example, we are using the second page (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Step 5: Define the new page dimensions
Now you can set the new page size using the `SetPageSize()` method of the `Page` object. In this example, we're setting the page dimensions to A4 (11.7 x 8.3 inches), converted to points (1 inch = 72 points).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Step 6: Save the updated document
Finally, you can save the updated PDF document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Update Dimensions using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Get page collection
PageCollection pageCollection = pdfDocument.Pages;
// Get particular page
Page pdfPage = pageCollection[1];
// Set the page size as A4 (11.7 x 8.3 in) and in Aspose.Pdf, 1 inch = 72 points
// So A4 dimensions in points will be (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Save the updated document
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Conclusion
In this tutorial, we learned how to update the dimensions of a page in a PDF document using Aspose.PDF for .NET. By following this step-by-step guide, you can easily change the dimensions of a page in a PDF document as needed. Aspose.PDF offers a powerful and flexible API for working with PDF files and performing various manipulations, including changing page dimensions. With this knowledge, you can control and customize the dimensions of your PDF pages to meet your specific needs.

### FAQ's for update PDF page dimensions

#### Q: How can I update the dimensions of a specific page in a PDF document using Aspose.PDF for .NET?

A: To update the dimensions of a specific page in a PDF document using Aspose.PDF for .NET, you can follow these steps:

1. Set the document directory by specifying the path where your original PDF file is located and where you want to save the updated PDF file. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.
2. Open the existing PDF document to update using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the original PDF document.
3. Access the pages collection of the PDF document using the `Pages` property of the `Document` class.
4. Select the specific page you want to update from the page collection using the index of the page. In the provided C# source code, we are using the second page (index 1).
5. Define the new page size using the `SetPageSize()` method of the `Page` object. In the example, we set the page dimensions to A4 size (11.7 x 8.3 inches), converted to points (1 inch = 72 points).
6. Save the updated PDF document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

#### Q: Can I update the dimensions of multiple pages in the PDF document simultaneously?

A: Yes, you can modify the provided source code to update the dimensions of multiple pages in the PDF document simultaneously. Instead of selecting a specific page (as shown in step 4), you can loop through all the pages in the page collection and set the desired page size for each page.

#### Q: How do I convert page dimensions from inches to points when using Aspose.PDF for .NET?

A: In Aspose.PDF for .NET, the measurement unit used for page dimensions is points, where 1 inch is equivalent to 72 points. To convert inches to points, you can use the formula: `points = inches * 72`. For example, to set a page size of 11.7 x 8.3 inches, you can calculate the corresponding dimensions in points as (11.7 * 72) and (8.3 * 72).

#### Q: Will updating the dimensions of a page affect the content layout of the PDF document?

A: Yes, updating the dimensions of a page will affect the content layout of the PDF document on that specific page. When you change the page dimensions, the content on the page will be adjusted accordingly to fit within the new dimensions.

#### Q: Is it possible to revert the changes and restore the original page dimensions after updating them?

A: Yes, if you want to revert the changes and restore the original page dimensions, you can either keep a copy of the original PDF document before making changes or re-open the original PDF document again without saving the changes. This way, the original dimensions will be preserved.
