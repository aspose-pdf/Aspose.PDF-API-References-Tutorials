---
title: Text in Header
linktitle: Text in Header
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add text in the header of a PDF document with Aspose.PDF for .NET.
type: docs
weight: 190
url: /net/programming-with-stamps-and-watermarks/text-in-header/
---
In this tutorial, we are going to learn how to add text in the header of a PDF document using Aspose.PDF for .NET. Follow the steps below:

## Step 1: Project preparation

Make sure you have installed Aspose.PDF for .NET and created a C# project.

## Step 2: Importing namespaces

Add the following namespaces to your C# source file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Opening the document

Open the existing PDF document using the path provided:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 4: Creating Header Text

Create a new text stamp with the text you want to add in the header:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

You can customize the text by changing its properties like top margin, horizontal alignment, and vertical alignment.

## Step 5: Add header text to all pages

Go through all the pages of the PDF document and add the text stamp in the header:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Step 6: Saving the PDF Document

Once the header text has been added on all pages, save the updated PDF document:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where you want to save the PDF document.

### Sample source code for Textin Header using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Create header
TextStamp textStamp = new TextStamp("Header Text");

// Set properties of the stamp
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Add header on all pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Save updated document
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Congratulation ! You have learned how to add text in the header of a PDF document using Aspose.PDF for .NET. You can now customize your headers by adding additional text to your PDF documents.

