---
title: Delete Particular Bookmark
linktitle: Delete Particular Bookmark
second_title: Aspose.PDF for .NET API Reference
description: Easily delete a particular bookmark from your PDF files with Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-bookmarks/delete-particular-bookmark/
---

It may be necessary to delete a particular bookmark from a PDF document. With Aspose.PDF for .NET, you can easily delete a particular bookmark by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file from which you want to remove a particular bookmark. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we are going to open the PDF document from which we want to remove a bookmark using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Step 4: Delete a particular bookmark

In this step, we delete a particular bookmark using the `Delete` method of the `Outlines` property. We specify the title of the bookmark to delete. Here is the corresponding code:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Step 5: Save the updated file

Finally, we save the updated PDF file using the `Save` method of the `pdfDocument` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Delete Particular Bookmark using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Delete particular outline by Title
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Save updated file
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step by step guide to delete a particular bookmark with Aspose.PDF for .NET. You can use this code to target and remove specific bookmarks from your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
