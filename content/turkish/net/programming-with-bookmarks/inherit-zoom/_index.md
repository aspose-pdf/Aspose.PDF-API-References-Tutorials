---
title: Inherit Zoom In PDF File
linktitle: Inherit Zoom In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily inherit bookmark zoom in PDF file with Aspose.PDF for .NET.
type: docs
weight: 90
url: /tr/net/programming-with-bookmarks/inherit-zoom/
---
Zoom inheritance in PDF file allows you to specify a default zoom level for bookmarks. With Aspose.PDF for .NET, you can easily inherit zoom by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to inherit the zoom from. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we are going to open the PDF document on which we want to inherit the zoom using the following code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Step 4: Get Bookmarks Collection

In this step, we will get the collection of bookmarks or landmarks of the document using the `Outlines` property of the `doc` object. Here is the corresponding code:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Step 5: Set Zoom Level

Now we will set the zoom level by creating an `XYZExplicitDestination` object with the specified x, y and z coordinates. Here we use the coordinates (100, 100, 0) with a zoom of 2. Here is the corresponding code:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Step 6: Add Zoom Level to Bookmarks

In this step, we add the `XYZExplicitDestination` object as an action to the bookmarks of the `item` collection. Here is the corresponding code:

```csharp
item. Action = new GoToAction(dest);
```

## Step 7: Add the updated bookmarks to the document

Finally, we add the updated bookmarks to the document's bookmarks collection using the `Add` method of the `doc.Outlines` object. Here is the corresponding code:

```csharp
doc. Outlines. Add(item);
```

## Step 8: Save the updated file

Now let's save the updated PDF file using the `Save` method of the `doc` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Inherit Zoom using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document doc = new Document(dataDir + "input.pdf");
// Get outlines/bookmarks collection of PDF file
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Set zoom level as 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Add XYZExplicitDestination as action to outlines collection of PDF
item.Action = new GoToAction(dest);
// Add item to outlines collection of PDF file
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Save output
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step by step guide to Inherit Zoom with Aspose.PDF for .NET. You can use this code to specify a default zoom level for bookmarks in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.

### FAQ's for inherit zoom in PDF file

#### Q: What is zoom inheritance in a PDF file?

A: Zoom inheritance refers to the ability to specify a default zoom level for bookmarks in a PDF document. This allows for consistent and user-friendly navigation when users interact with the bookmarks.

#### Q: Why would I want to inherit zoom levels for bookmarks?

A: Inheriting zoom levels ensures that users have a consistent viewing experience when navigating through bookmarks in a PDF document. It can be particularly useful when you want to provide a specific view for different sections of a document.

#### Q: How do I import the necessary libraries for my C# project?

A: To import the required libraries for your C# project, include the following import directives:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

These directives enable you to access the classes and methods needed to work with PDF documents and bookmarks.

#### Q: How do I specify the path to the documents folder?

A: In the provided source code, replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the folder containing the PDF file for which you want to inherit zoom levels.

#### Q: How do I open a PDF document to inherit zoom levels?

A: To open a PDF document for inheriting zoom levels, use the following code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Replace `"input.pdf"` with the actual file name.

#### Q: How do I set the zoom level for bookmarks?

A: To set the zoom level, create an `XYZExplicitDestination` object with the desired coordinates and zoom factor. Here's an example:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

This sets the zoom level to 2 at coordinates (100, 100).

#### Q: How do I add the zoom level to bookmarks?

A: Add the `XYZExplicitDestination` object as an action to the bookmarks collection:

```csharp
item.Action = new GoToAction(dest);
```

Where `item` is an `OutlineItemCollection` representing a bookmark.

#### Q: How do I save the updated PDF file?

A: Save the updated PDF file using the `Save` method of the `doc` object:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Q: Can I customize zoom levels for different bookmarks?

A: Yes, you can customize the zoom levels for different bookmarks by creating multiple `XYZExplicitDestination` objects with different coordinates and zoom factors.

#### Q: Is there a limit to the number of bookmarks I can apply zoom inheritance to?

A: There is typically no strict limit to the number of bookmarks you can apply zoom inheritance to. However, very large documents with an excessive number of bookmarks may require efficient memory management.

#### Q: How can I confirm that the zoom inheritance has been applied?

A: Open the generated PDF file to verify that the specified zoom levels have been inherited by the bookmarks.