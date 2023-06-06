---
title: Get Bookmark Page Number
linktitle: Get Bookmark Page Number
second_title: Aspose.PDF for .NET API Reference
description: Easily get bookmark page numbers from your PDF files with Aspose.PDF for .NET.
type: docs
weight: 60
url: /net/programming-with-bookmarks/get-bookmark-page-number/
---

Retrieving page numbers associated with bookmarks in a PDF document can be useful for navigation. With Aspose.PDF for .NET, you can easily get the page number of bookmarks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf.Facades;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to extract the bookmark page numbers from. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Create the bookmark editor

Now we will create a `PdfBookmarkEditor` object to manipulate the bookmarks of the document. Use the following code:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Step 4: Open the PDF File

In this step, we open the PDF file using the `BindPdf` method of the bookmark editor. Here is the corresponding code:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Step 5: Extract bookmarks

Now we will extract the bookmarks from the document using the `ExtractBookmarks` method of the bookmark editor. Here is the corresponding code:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Step 6: Browse bookmarks and get page numbers

Finally, we loop through the extracted bookmarks and get the page numbers associated with each bookmark using a `foreach` loop. Here is the corresponding code:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Sample source code for Get Bookmark Page Number using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Open PDF file
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Extract bookmarks
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Conclusion

Congratulation ! Now you have a step by step guide to getting bookmark page numbers with Aspose.PDF for .NET. You can use this code to retrieve the navigation information associated with each bookmark in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
