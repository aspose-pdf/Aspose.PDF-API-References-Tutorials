---
title: Add Child Bookmark
linktitle: Add Child Bookmark
second_title: Aspose.PDF for .NET API Reference
description: Easily add child bookmark to your PDF files for more organized browsing with Aspose.PDF for .NET.
type: docs
weight: 20
url: /net/programming-with-bookmarks/add-child-bookmark/
---

Adding child bookmarks to a PDF document allows for more structured organization and navigation. With Aspose.PDF for .NET, you can easily add a sub-bookmark by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to add a sub-bookmark. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document to which we want to add a sub-bookmark using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Step 4: Create parent bookmark object

In this step, we will create a parent bookmark object using the `OutlineItemCollection` class and set its properties such as title, italic attribute and bold attribute. Here is the corresponding code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Step 5: Create Child Bookmark Object

In this step, we will create a sub-bookmark object again using the `OutlineItemCollection` class and set its properties. Here is the corresponding code:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Step 6: Add the sub-bookmark to the parent bookmark

Finally, we add the created subbookmark to the parent bookmark's subbookmark collection using the `Add` method of the parent object. Here is the corresponding code:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Step 7: Add the parent bookmark to the document's bookmark collection

Finally, we add the parent bookmark to the document's bookmark collection using the `Add` method of the `Outlines` property. Here is the corresponding code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Sample source code for Add Child Bookmark using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Create a parent bookmark object
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Create a child bookmark object
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Add child bookmark in parent bookmark's collection
pdfOutline.Add(pdfChildOutline);
// Add parent bookmark in the document's outline collection.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Save output
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step by step guide to add a sub-bookmark with Aspose.PDF for .NET. You can use this code to organize and structure your bookmarks in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
