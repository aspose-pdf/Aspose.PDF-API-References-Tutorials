---
title: Textin Header
linktitle: Textin Header
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 190
url: /net/programming-with-stamps-and-watermarks/textin-header/
---
### Sample source code for Textin Header using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");
            // Create header
            TextStamp textStamp = new TextStamp("Header Text");
            // Set properties of the stamp
            textStamp.TopMargin = 10;
            textStamp.HorizontalAlignment = HorizontalAlignment.Center;
            textStamp.VerticalAlignment = VerticalAlignment.Top;
            // Add header on all pages
            foreach (Page page in pdfDocument.Pages)
            {
                page.AddStamp(textStamp);
            }
            // Save updated document
            pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
            Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);
```