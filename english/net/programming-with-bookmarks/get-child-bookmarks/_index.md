---
title: Get Child Bookmarks
linktitle: Get Child Bookmarks
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /net/programming-with-bookmarks/get-child-bookmarks/
---
### Sample source code for Get Child Bookmarks using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
            // Loop through all the bookmarks
            foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
            {
                Console.WriteLine(outlineItem.Title);
                Console.WriteLine(outlineItem.Italic);
                Console.WriteLine(outlineItem.Bold);
                Console.WriteLine(outlineItem.Color);
                if (outlineItem.Count > 0)
                {
                    Console.WriteLine("Child Bookmarks");
                    // There are child bookmarks then loop through that as well
                    foreach (OutlineItemCollection childOutline in outlineItem)
                    {
                        Console.WriteLine(childOutline.Title);
                        Console.WriteLine(childOutline.Italic);
                        Console.WriteLine(childOutline.Bold);
                        Console.WriteLine(childOutline.Color);
                    }
                }
            }
```