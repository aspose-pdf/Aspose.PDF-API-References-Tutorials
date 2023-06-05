---
title: Add Bookmark
linktitle: Add Bookmark
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /net/programming-with-bookmarks/add-bookmark/
---
### Sample source code for Add Bookmark using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Bookmarks();
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