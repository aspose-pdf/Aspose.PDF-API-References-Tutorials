---
title: Expand Bookmarks
linktitle: Expand Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: Easily expand bookmarks of your PDF files for improved navigation with Aspose.PDF for .NET.
type: docs
weight: 50
url: /net/programming-with-bookmarks/expand-bookmarks/
---

Expanding bookmarks in a PDF document will display all open bookmarks by default. With Aspose.PDF for .NET, you can easily expand bookmarks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file whose bookmarks you want to expand. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document whose bookmarks we want to expand using the following code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Step 4: Set Page Display Mode

In this step, we will set the page display mode to show bookmarks by default. We use the `PageMode` property of the `doc` object to set the desired page mode. Here is the corresponding code:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Step 5: Browse bookmarks and expand them

Now we'll loop through each bookmark item in the document's bookmarks collection and set each item's open state to `true` to expand them by default. Here is the corresponding code:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Step 6: Save the updated file

Finally, we save the updated PDF file using the `Save` method of the `doc` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Expand Bookmarks using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document doc = new Document(dataDir + "input.pdf");
// Set page view mode i.e. show thumbnails, full-screen, show attachment panel
doc.PageMode = PageMode.UseOutlines;
// Traverse through each Ouline item in outlines collection of PDF file
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Set open status for outline item
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Save output
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You now have a step-by-step guide to developing bookmarks with Aspose.PDF for .NET. You can use this code to show all default bookmarks in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.
