---
title: Delete Particular Bookmark
linktitle: Delete Particular Bookmark
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/programming-with-bookmarks/delete-particular-bookmark/
---
### Sample source code for Delete Particular Bookmark using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Bookmarks();
            // Open document
            Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
            // Delete particular outline by Title
            pdfDocument.Outlines.Delete("Child Outline");
            dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
            // Save updated file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```