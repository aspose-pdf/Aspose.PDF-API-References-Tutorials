---
title: Get Child Bookmarks
linktitle: Get Child Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: Easily get child bookmarks of your PDF files with Aspose.PDF for .NET.
type: docs
weight: 80
url: /net/programming-with-bookmarks/get-child-bookmarks/
---

Retrieving child bookmarks from a PDF document can be useful for exploring the hierarchical structure of bookmarks. With Aspose.PDF for .NET, you can easily get the child bookmarks by following the following source code:

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
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## Step 4: Browse bookmarks and child bookmarks

In this step, we will iterate over all the bookmarks in the document using a `foreach` loop. For each bookmark, we will display the information such as title, italic style, bold style and color. If the bookmark has child bookmarks, we'll display those as well. Here is the corresponding code:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Browse child bookmarks as well
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Sample source code for Get Child Bookmarks using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Loop through all the bookmarks
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// There are child bookmarks then loop through that as well
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Conclusion

Congratulation ! Now you have a step by step guide to get child bookmarks with Aspose.PDF for .NET. You can use this code to explore the hierarchical structure of bookmarks and get detailed information about each bookmark and its child bookmarks in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
