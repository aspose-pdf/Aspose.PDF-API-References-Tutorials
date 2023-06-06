---
title: Textin Footer
linktitle: Textin Footer
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 180
url: /net/programming-with-stamps-and-watermarks/textin-footer/
---
### Sample source code for Textin Footer using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");
            // Create footer
            TextStamp textStamp = new TextStamp("Footer Text");
            // Set properties of the stamp
            textStamp.BottomMargin = 10;
            textStamp.HorizontalAlignment = HorizontalAlignment.Center;
            textStamp.VerticalAlignment = VerticalAlignment.Bottom;
            // Add footer on all pages
            foreach (Page page in pdfDocument.Pages)
            {
                page.AddStamp(textStamp);
            }
            dataDir = dataDir + "TextinFooter_out.pdf";
            // Save updated PDF file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);
```