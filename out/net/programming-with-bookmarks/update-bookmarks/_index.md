---
title: Update Bookmarks
linktitle: Update Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: Easily update bookmarks in your PDF files with Aspose.PDF for .NET.
type: docs
weight: 100
url: /content/net/programming-with-bookmarks/update-bookmarks/
---

Updating bookmarks in a PDF document is often necessary to reflect changes or updates in the structure or content of the document. With Aspose.PDF for .NET, you can easily update bookmarks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to update. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document we want to update using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## Step 4: Get bookmark object

In this step, we'll get the specific bookmark object we want to update. In the example below, we retrieve the bookmark at index 1 (the second bookmark in the bookmarks collection). You can adjust the index according to your needs. Here is the corresponding code:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Step 5: Update bookmark properties

Now let's update the bookmark properties such as title, italic style, and bold style. You can adjust these properties according to your needs. Here is the corresponding code:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Step 6: Save the updated file

Now let's save the updated PDF file using the `Save` method of the `pdfDocument` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Update Bookmarks using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// Get a bookmark object
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// Save output
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step-by-step guide to updating bookmarks with Aspose.PDF for .NET. You can use this code to change the titles and styles of bookmarks in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.