---
title: Image In Footer
linktitle: Image In Footer
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 130
url: /net/programming-with-stamps-and-watermarks/image-in-footer/
---
### Sample source code for Image In Footer using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");
            // Create footer
            ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");
            // Set properties of the stamp
            imageStamp.BottomMargin = 10;
            imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
            imageStamp.VerticalAlignment = VerticalAlignment.Bottom;
            // Add footer on all pages
            foreach (Page page in pdfDocument.Pages)
            {
                page.AddStamp(imageStamp);
            }
            dataDir = dataDir + "ImageInFooter_out.pdf";
            // Save updated PDF file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```