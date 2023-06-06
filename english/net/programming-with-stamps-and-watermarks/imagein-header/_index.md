---
title: Imagein Header
linktitle: Imagein Header
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 140
url: /net/programming-with-stamps-and-watermarks/imagein-header/
---
### Sample source code for Imagein Header using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");
            // Create header
            ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");
            // Set properties of the stamp
            imageStamp.TopMargin = 10;
            imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
            imageStamp.VerticalAlignment = VerticalAlignment.Top;
            // Add header on all pages
            foreach (Page page in pdfDocument.Pages)
            {
                page.AddStamp(imageStamp);
            }
            dataDir = dataDir + "ImageinHeader_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        
```