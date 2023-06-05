---
title: Add Child Bookmark
linktitle: Add Child Bookmark
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /net/programming-with-bookmarks/add-child-bookmark/
---
### Sample source code for Add Child Bookmark using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Bookmarks();
            // Open document
            Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
            // Create a parent bookmark object
            OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
            pdfOutline.Title = "Parent Outline";
            pdfOutline.Italic = true;
            pdfOutline.Bold = true;      
            // Create a child bookmark object
            OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
            pdfChildOutline.Title = "Child Outline";
            pdfChildOutline.Italic = true;
            pdfChildOutline.Bold = true;
            // Add child bookmark in parent bookmark's collection
            pdfOutline.Add(pdfChildOutline);
            // Add parent bookmark in the document's outline collection.
            pdfDocument.Outlines.Add(pdfOutline);
            dataDir = dataDir + "AddChildBookmark_out.pdf";
            // Save output
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```