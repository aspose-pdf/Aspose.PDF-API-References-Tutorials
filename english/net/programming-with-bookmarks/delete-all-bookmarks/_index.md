---
title: Delete All Bookmarks
linktitle: Delete All Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /net/programming-with-bookmarks/delete-all-bookmarks/
---
### Sample source code for Delete All Bookmarks using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Bookmarks();
            // Open document
            Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
            // Delete all bookmarks
            pdfDocument.Outlines.Delete();
            dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
            // Save updated file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```