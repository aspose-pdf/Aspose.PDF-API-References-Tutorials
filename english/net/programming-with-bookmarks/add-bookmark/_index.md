---
title: Add Bookmark
linktitle: Add Bookmark
second_title: Aspose.PDF for .NET API Reference
description: Easily add bookmarks to your PDF files for improved navigation with Aspose.PDF for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/add-bookmark/
---

Adding bookmarks in a PDF document allows easy and quick navigation. With Aspose.PDF for .NET, you can easily add a bookmark by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to add a bookmark to. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document to which we want to add a bookmark using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Step 4: Create bookmark object

In this step, we will create a bookmark object using `OutlineItemCollection` class and set its properties such as title, italic attribute, bold attribute and action to perform when clicked. Here is the corresponding code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Step 5: Add bookmark to document

Finally, we add the created bookmark to the document's bookmark collection using the `Add` method of the `Outlines` property. Here is the corresponding code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Sample source code for Add Bookmark using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Create a bookmark object
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Set the destination page number
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Add bookmark in the document's outline collection.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Save output
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step by step guide to add a bookmark using Aspose.PDF for .NET. You can use this code to improve navigation in your PDF documents by adding custom bookmarks.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
