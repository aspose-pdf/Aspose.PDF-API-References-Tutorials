---
title: Get Bookmarks
linktitle: Get Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: Easily bookmark your PDF files with Aspose.PDF for .NET.
type: docs
weight: 70
url: /net/programming-with-bookmarks/get-bookmarks/
---

Retrieving bookmarks from a PDF document can be useful for analyzing the document's structure and navigational information. With Aspose.PDF for .NET, you can easily get the bookmarks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to extract the bookmarks from. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we are going to open the PDF document from which we want to extract the bookmarks using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## Step 4: Browse Bookmarks

In this step, we will iterate over all the bookmarks in the document using a `foreach` loop. For each bookmark, we will display the information such as title, italic style, bold style and color. Here is the corresponding code:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### Sample source code for Get Bookmarks using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// Loop through all the bookmarks
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## Conclusion

Congratulation ! Now you have a step by step guide to get bookmarks with Aspose.PDF for .NET. You can use this code to parse bookmarks and extract information associated with each bookmark in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
