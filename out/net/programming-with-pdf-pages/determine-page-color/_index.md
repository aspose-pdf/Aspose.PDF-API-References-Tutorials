---
title: Determine Page Color
linktitle: Determine Page Color
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to determining PDF page color with Aspose.PDF for .NET. Analyze and display the color type of each page. Easy to implement.
type: docs
weight: 40
url: /content/net/programming-with-pdf-pages/determine-page-color/
---
In this tutorial, we'll walk you through the step-by-step process to determine the page color of a PDF using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to determine the page color of a PDF using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where your PDF file is located. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF file
Then you can open the PDF file to analyze using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Step 3: Analyze the pages
Now you can loop through all pages of the PDF document using a `for` loop. For each page, you can get the color type of the page using the `ColorType` property of the `Page` object and display it in the console.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     ColorType pageColorType = pdfDocument.Pages[pageCount].ColorType;
     switch(pageColorType)
     {
         box ColorType.BlackAndWhite:
             Console.WriteLine("Page #" + pageCount + " is black and white.");
             break;
         ColorType.Grayscale box:
             Console.WriteLine("Page #" + pageCount + " is grayscale.");
             break;
         box ColorType.Rgb:
             Console.WriteLine("Page #" + pageCount + " is in RGB colors.");
             break;
         box ColorType.Undefined:
             Console.WriteLine("Page #" + pageCount + " has undefined color.");
             break;
     }
}
```

### Sample source code for Determine Page Color using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open source PDF file
Document pdfDocument = new Document( dataDir + "input.pdf");
// Iterate through all the page of PDF file
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	// Get the color type information for particular PDF page
	Aspose.Pdf.ColorType pageColorType = pdfDocument.Pages[pageCount].ColorType;
	switch (pageColorType)
	{
		case ColorType.BlackAndWhite:
			Console.WriteLine("Page # -" + pageCount + " is Black and white..");
			break;
		case ColorType.Grayscale:
			Console.WriteLine("Page # -" + pageCount + " is Gray Scale...");
			break;
		case ColorType.Rgb:
			Console.WriteLine("Page # -" + pageCount + " is RGB..", pageCount);
			break;
		case ColorType.Undefined:
			Console.WriteLine("Page # -" + pageCount + " Color is undefined..");
			break;
	}
}

```

## Conclusion
In this tutorial, we learned how to determine the page color of a PDF using Aspose.PDF for .NET. By following the steps outlined above, you can easily implement this functionality in your own projects. Feel free to explore the Aspose.PDF documentation further to discover other useful features for working with PDF files.