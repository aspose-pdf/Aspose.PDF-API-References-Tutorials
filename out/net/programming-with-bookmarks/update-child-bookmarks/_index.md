---
title: Update Child Bookmarks
linktitle: Update Child Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: Easily update child bookmarks in your PDF files with Aspose.PDF for .NET.
type: docs
weight: 110
url: /content/net/programming-with-bookmarks/update-child-bookmarks/
---

Updating child bookmarks in a PDF document allows you to modify the properties of specific bookmarks within a parent bookmark. With Aspose.PDF for .NET, you can easily update child bookmarks by following the following source code:

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
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Step 4: Get parent bookmark object

In this step, we are going to get the specific parent bookmark object from which we want to update the child bookmarks. In the example below, we retrieve the parent bookmark at index 1 (the second bookmark in the bookmarks collection). You can adjust the index according to your needs. Here is the corresponding code:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Step 5: Get Child Bookmark Object

Now let's get the specific child bookmark object we want to update. In the example below, we retrieve the child bookmark at index 1 (the second child bookmark in the collection of child bookmarks of the parent bookmark). You can adjust the index according to your needs. Here is the corresponding code:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## Step 6: Update child bookmark properties

Now let's update the child bookmark properties such as title, italic style, and bold style. You can adjust these properties according to your needs. Here is the corresponding code:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## Step 7: Save the updated file

Now let's save the updated PDF file using the `Save` method of the `pdfDocument` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Update Child Bookmarks using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Get a bookmark object
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// Get child bookmark object
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Save output
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You now have a step-by-step guide to updating child bookmarks with Aspose.PDF for .NET. You can use this code to modify the properties of child bookmarks in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.