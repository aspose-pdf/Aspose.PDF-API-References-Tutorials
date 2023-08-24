---
title: Add Child Bookmark In PDF File
linktitle: Add Child Bookmark In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily add child bookmark in PDF file for more organized browsing with Aspose.PDF for .NET.
type: docs
weight: 20
url: /zh/net/programming-with-bookmarks/add-child-bookmark/
---
Adding child bookmarks in PDF file allows for more structured organization and navigation. With Aspose.PDF for .NET, you can easily add a sub-bookmark by following the following source code:

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

### Sample source code for Add Child Bookmark using Aspose.PDF for .NET 
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

### FAQ's for add child bookmark in PDF file

#### Q: What are child bookmarks in a PDF file?

A: Child bookmarks, also known as sub-bookmarks, are navigational elements within a PDF document that are hierarchically structured under a parent bookmark. They provide a way to create a more organized and detailed table of contents for the document.

#### Q: How do I import the necessary libraries for my C# project?

A: To import the required libraries for your C# project, you can use the following import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

These libraries provide the necessary classes and functions for working with PDF documents and interactive features.

#### Q: How do I specify the path to the documents folder?

A: In the source code provided, you need to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the folder containing the PDF file you want to work with. This ensures that the code correctly locates the target PDF file.

#### Q: Can I create multiple levels of child bookmarks?

A: Yes, you can create multiple levels of child bookmarks by extending the process outlined in the tutorial. By creating parent bookmarks with sub-bookmarks and further nesting them, you can create a hierarchical structure of bookmarks for complex PDF documents.

#### Q: What is the purpose of the `OutlineItemCollection` class?

A: The `OutlineItemCollection` class in Aspose.PDF for .NET is used to create and manage outlines, which are essentially bookmarks in a PDF document. This class allows you to set properties such as title, font style, and actions for bookmarks.

#### Q: How do I add a sub-bookmark to a parent bookmark?

A: To add a sub-bookmark to a parent bookmark, you create a new `OutlineItemCollection` object for the sub-bookmark and set its properties. Then, you use the `Add` method of the parent bookmark's `OutlineItemCollection` to add the sub-bookmark to the parent's collection.

#### Q: Can I customize the appearance of child bookmarks?

A: Yes, similar to parent bookmarks, you can customize the appearance of child bookmarks by setting properties such as title, font style, and other attributes. This allows you to create visually distinctive and informative bookmarks.

#### Q: Is Aspose.PDF for .NET compatible with other programming languages?

A: Aspose.PDF for .NET is specifically designed for C# and .NET environments. However, Aspose offers similar libraries for other programming languages such as Java and Android, each tailored to their respective platforms.

#### Q: How do child bookmarks improve PDF navigation?

A: Child bookmarks improve PDF navigation by providing a more structured and organized table of contents. Users can quickly access specific sections of the document through the hierarchical bookmark structure.