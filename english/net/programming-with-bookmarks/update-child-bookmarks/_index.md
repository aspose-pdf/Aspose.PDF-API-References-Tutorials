---
title: Update Child Bookmarks
linktitle: Update Child Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /net/programming-with-bookmarks/update-child-bookmarks/
---
### Sample source code for Update Child Bookmarks using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
            // Get a bookmark object
            OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
            // Get child bookmark object
            OutlineItemCollection childOutline = pdfOutline[1];
            childOutline.Title = "Updated Outline";
            childOutline.Italic = true;
            childOutline.Bold = true;
            dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
            // Save output
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```