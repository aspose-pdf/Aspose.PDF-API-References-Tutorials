---
title: Add Bookmark In PDF File
linktitle: Add Bookmark In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily add bookmark in PDF file for improved navigation with Aspose.PDF for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/add-bookmark/
---
Adding bookmarks in a PDF file allows easy and quick navigation. With Aspose.PDF for .NET, you can easily add a bookmark in PDF file by following the following source code:

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

### Sample source code for Add Bookmark using Aspose.PDF for .NET 
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


### FAQ's for add bookmark in PDF file

#### Q: What are bookmarks in a PDF file?

A: Bookmarks, also known as outlines, are interactive elements that provide navigation and structure within a PDF document. They allow users to quickly jump to specific sections or pages.

#### Q: Why would I need to add bookmarks to a PDF file?

A: Adding bookmarks to a PDF file improves user experience and makes it easier for readers to navigate through the document's content. Bookmarks can serve as a table of contents or provide quick access to important sections.

#### Q: How do I import the required libraries for my C# project?

A: To import the necessary libraries for your C# project, include the following import directives:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

These directives enable you to access the classes and methods needed for working with PDF documents and bookmarks.

#### Q: How do I specify the path to the documents folder?

A: Replace `"YOUR DOCUMENT DIRECTORY"` in the provided source code with the actual path to the folder containing the PDF file you want to add a bookmark to.

#### Q: How do I open a PDF document for adding bookmarks?

A: To open a PDF document for adding bookmarks, use the following code:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

Replace `"AddBookmark.pdf"` with the actual file name.

#### Q: How do I create a bookmark object?

A: To create a bookmark object, use the `OutlineItemCollection` class. Customize its properties such as title, italic style, bold style, and action to perform when clicked.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

#### Q: What is the purpose of the `Action` property in a bookmark?

A: The `Action` property specifies the action to be performed when the bookmark is clicked. In this example, we use the `GoToAction` class to navigate to a specific page (page 2 in this case).

#### Q: How do I add the bookmark to the document?

A: Use the `Add` method of the `Outlines` property to add the created bookmark to the document's bookmark collection.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### Q: Can I add multiple bookmarks using this method?

A: Yes, you can repeat steps 4 to 8 to add multiple bookmarks to the document. Customize each bookmark's properties and actions as needed.

#### Q: How do I save the updated PDF file?

A: Save the updated PDF file using the `Save` method of the `pdfDocument` object:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### Q: How can I confirm that the bookmarks have been added?

A: Open the generated PDF file to verify that the specified bookmarks have been added to the document.

#### Q: Is there a limit to the number of bookmarks I can add?

A: There is generally no strict limit to the number of bookmarks you can add, but consider the document's size and complexity for optimal performance.

#### Q: Can I customize the appearance of bookmarks?

A: Yes, you can further customize bookmark appearance, color, style, and other attributes using Aspose.PDF features.