---
title: Get Bookmark Page Number In PDF File
linktitle: Get Bookmark Page Number In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily get bookmark page number in PDF file with Aspose.PDF for .NET.
type: docs
weight: 60
url: /zh/net/programming-with-bookmarks/get-bookmark-page-number/
---
Retrieving page numbers associated with bookmarks in PDF file can be useful for navigation. With Aspose.PDF for .NET, you can easily get the page number of bookmarks by following the following source code:

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

### FAQ's for get bookmark page number in PDF file

#### Q: What are bookmarks in a PDF file?

A: Bookmarks in a PDF file are navigational aids that allow users to quickly jump to specific sections or pages within the document. They enhance the user experience by providing shortcuts to relevant content.

#### Q: Why would I want to retrieve bookmark page numbers from a PDF file?

A: Retrieving bookmark page numbers helps users navigate through a document more effectively, providing a clear indication of where each bookmark leads. This is particularly useful for longer documents with multiple sections.

#### Q: How do I import the necessary libraries for my C# project?

A: To import the required library for your C# project, use the following import directive:

```csharp
using Aspose.Pdf.Facades;
```

This directive allows you to utilize the classes and methods provided by Aspose.PDF for .NET.

#### Q: How do I specify the path to the documents folder?

A: In the provided source code, replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the folder containing the PDF file from which you want to extract bookmark page numbers. This ensures that the code can locate the target PDF file.

#### Q: How do I create a bookmark editor?

A: To create a bookmark editor, use the following code:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Q: How do I open a PDF file for bookmark manipulation?

A: To open a PDF file for extracting bookmark information, use the following code:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

Replace `"GetBookmarks.pdf"` with the actual file name.

#### Q: How do I extract bookmarks from the PDF file?

A: To extract bookmarks from the PDF file, use the `ExtractBookmarks` method of the bookmark editor:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Q: How do I retrieve and display bookmark page numbers?

A: Loop through the extracted bookmarks using a `foreach` loop and access the `PageNumber` property of each bookmark to retrieve and display its associated page number:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Q: Can I modify bookmark properties using this approach?

A: While this tutorial focuses on retrieving bookmark page numbers, you can modify other bookmark properties using the same `Bookmark` object and associated properties.

#### Q: How do I save the updated PDF file after extracting bookmark information?

A: Bookmark extraction does not modify the original PDF file. If you want to save any changes, you can do so using other methods provided by Aspose.PDF for .NET.