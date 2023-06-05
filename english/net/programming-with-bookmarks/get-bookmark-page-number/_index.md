---
title: Get Bookmark Page Number
linktitle: Get Bookmark Page Number
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /net/programming-with-bookmarks/get-bookmark-page-number/
---
### Sample source code for Get Bookmark Page Number using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create PdfBookmarkEditor
            PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
            // Open PDF file
            bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
            // Extract bookmarks
            Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
            foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
            {
                string strLevelSeprator = string.Empty;
                for (int i = 1; i < bookmark.Level; i++)
                {
                    strLevelSeprator += "----";
                }
                Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
                Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
                Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
            }
```