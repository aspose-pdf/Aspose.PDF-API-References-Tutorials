---
title: Delete All Bookmarks
linktitle: Delete All Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: Easily delete all bookmarks from your PDF files with Aspose.PDF for .NET.
type: docs
weight: 30
url: /net/programming-with-bookmarks/delete-all-bookmarks/
---

# Delete all bookmarks with Aspose.PDF for .NET

Deleting bookmarks from a PDF document may be necessary in some cases. With Aspose.PDF for .NET, you can easily remove all bookmarks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file from which you want to remove bookmarks. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we are going to open the PDF document from which we want to remove the bookmarks using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Step 4: Delete all bookmarks

In this step, we delete all bookmarks from the document using the `Delete` method of the `Outlines` property. Here is the corresponding code:

```csharp
pdfDocument.Outlines.Delete();
```

## Step 5: Save the updated file

Finally, we save the updated PDF file using the `Save` method of the `pdfDocument` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Delete All Bookmarks using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Delete all bookmarks
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Save updated file
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step by step guide to remove all bookmarks with Aspose.PDF for .NET. You can use this code to clean up your PDF documents by deleting all existing bookmarks.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
