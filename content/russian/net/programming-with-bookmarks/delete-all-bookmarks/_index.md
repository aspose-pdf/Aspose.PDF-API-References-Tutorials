---
title: Delete All Bookmarks In PDF File
linktitle: Delete All Bookmarks In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily delete all bookmarks in PDF file with Aspose.PDF for .NET.
type: docs
weight: 30
url: /ru/net/programming-with-bookmarks/delete-all-bookmarks/
---
# Delete all bookmarks with Aspose.PDF for .NET

Deleting bookmarks in PDF file may be necessary in some cases. With Aspose.PDF for .NET, you can easily remove all bookmarks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file from which you want to remove bookmarks. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we are going to open the PDF document from which we want to remove the bookmarks using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Step 4: Delete all bookmarks

In this step, we delete all bookmarks from the document using the `Delete` method of the `Outlines` property. Here is the corresponding code:

```csharp
pdfDocument.Outlines.Delete();
```

## Step 5: Save the updated file

Finally, we save the updated PDF file using the `Save` method of the `pdfDocument` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Delete All Bookmarks using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Delete all bookmarks
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Save updated file
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! Now you have a step by step guide to remove all bookmarks with Aspose.PDF for .NET. You can use this code to clean up your PDF documents by deleting all existing bookmarks.

Be sure to check out the official Aspose.PDF documentation for more information on advanced bookmark manipulation features.

### FAQ's for delete all bookmarks in PDF file

#### Q: What are bookmarks in a PDF file?

A: Bookmarks in a PDF file are navigational aids that allow users to quickly jump to specific sections or pages within the document. They help organize and enhance the user experience when navigating through lengthy content.

#### Q: Why would I need to delete all bookmarks from a PDF file?

A: There might be cases where you want to remove all bookmarks from a PDF document to simplify its navigation, reorganize its structure, or prepare it for a specific purpose where bookmarks are not needed.

#### Q: How do I import the necessary libraries for my C# project?

A: To import the required library for your C# project, you can use the following import directive:

```csharp
using Aspose.Pdf;
```

This library provides the classes and methods needed to work with PDF documents.

#### Q: How do I specify the path to the documents folder?

A: In the source code provided, you need to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the folder containing the PDF file from which you want to remove bookmarks. This ensures that the code can locate the target PDF file.

#### Q: How do I open a PDF document for bookmark removal?

A: To open a PDF document for bookmark removal, use the following code:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

Replace `"DeleteAllBookmarks.pdf"` with the actual file name.

#### Q: How do I delete all bookmarks from the PDF document?

A: To remove all bookmarks from the PDF document, use the `Delete` method of the `Outlines` property:

```csharp
pdfDocument.Outlines.Delete();
```

#### Q: What happens to the rest of the content when bookmarks are deleted?

A: Deleting bookmarks does not affect the content or layout of the PDF document. Only the navigation bookmarks are removed, leaving the actual content intact.

#### Q: How do I save the updated PDF file after removing bookmarks?

A: To save the updated PDF file after deleting bookmarks, use the following code:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

#### Q: Can I selectively delete specific bookmarks instead of all of them?

A: Yes, you can selectively delete specific bookmarks by targeting them using their index or other properties. The provided source code demonstrates how to delete all bookmarks, but you can modify it to suit your needs.

#### Q: Are there any precautions I should take before deleting bookmarks?

A: Before deleting bookmarks, make sure to review the document to ensure that bookmark removal will not impact the document's usability or navigation. Consider making a backup of the original document before proceeding.