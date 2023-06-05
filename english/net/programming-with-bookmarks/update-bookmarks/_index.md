---
title: Update Bookmarks
linktitle: Update Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /net/programming-with-bookmarks/update-bookmarks/
---
### Sample source code for Update Bookmarks using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Bookmarks();
            // Open document
            Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
            // Get a bookmark object
            OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
            pdfOutline.Title = "Updated Outline";
            pdfOutline.Italic = true;
            pdfOutline.Bold = true;
            dataDir = dataDir + "UpdateBookmarks_out.pdf";
            // Save output
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```