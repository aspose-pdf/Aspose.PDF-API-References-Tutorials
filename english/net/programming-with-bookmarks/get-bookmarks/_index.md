---
title: Get Bookmarks
linktitle: Get Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /net/programming-with-bookmarks/get-bookmarks/
---
### Sample source code for Get Bookmarks using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
            // Loop through all the bookmarks
            foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
            {
                Console.WriteLine(outlineItem.Title);
                Console.WriteLine(outlineItem.Italic);
                Console.WriteLine(outlineItem.Bold);
                Console.WriteLine(outlineItem.Color);
            }
```