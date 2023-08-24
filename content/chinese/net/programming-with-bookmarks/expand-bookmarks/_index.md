---
title: Expand Bookmarks In PDF File
linktitle: Expand Bookmarks In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily expand bookmarks in PDF file for improved navigation with Aspose.PDF for .NET.
type: docs
weight: 50
url: /zh/net/programming-with-bookmarks/expand-bookmarks/
---
Expanding bookmarks in PDF file will display all open bookmarks by default. With Aspose.PDF for .NET, you can easily expand bookmarks by following the following source code:

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

### Sample source code for Expand Bookmarks using Aspose.PDF for .NET 
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

### FAQ's for expand bookmarks in PDF file

#### Q: What are bookmarks in a PDF file?

A: Bookmarks in a PDF file are navigational aids that allow users to quickly jump to specific sections or pages within the document. They provide a convenient way to access different parts of a document.

#### Q: Why would I want to expand bookmarks in a PDF file?

A: Expanding bookmarks can improve the user experience by displaying all bookmarks in an expanded state by default. This gives users a clear overview of the document's structure and allows them to easily navigate to different sections.

#### Q: How do I import the necessary libraries for my C# project?

A: To import the required library for your C# project, use the following import directive:

```csharp
using Aspose.Pdf;
```

This directive allows you to utilize the classes and methods provided by Aspose.PDF for .NET.

#### Q: How do I specify the path to the documents folder?

A: In the provided source code, replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the folder containing the PDF file that you want to work with. This ensures that the code can locate the target PDF file.

#### Q: How do I open a PDF document to expand its bookmarks?

A: To open a PDF document for expanding bookmarks, use the following code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Replace `"input.pdf"` with the actual file name.

#### Q: How do I set the page display mode to show bookmarks by default?

A: To set the page display mode to show bookmarks by default, use the `PageMode` property of the `doc` object:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Q: How do I expand all bookmarks in the PDF document?

A: To expand all bookmarks, loop through each bookmark item in the document's outlines collection and set the `Open` property to `true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Q: What happens if a bookmark has nested child bookmarks?

A: If a bookmark has nested child bookmarks, expanding the parent bookmark will also expand its child bookmarks, providing a comprehensive view of the document's structure.

#### Q: How do I save the updated PDF file after expanding bookmarks?

A: To save the updated PDF file after expanding bookmarks, use the following code:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Q: Can I customize the appearance of expanded bookmarks?

A: While this tutorial focuses on expanding bookmarks by default, you can customize the appearance of bookmarks using Aspose.PDF's other features and properties.