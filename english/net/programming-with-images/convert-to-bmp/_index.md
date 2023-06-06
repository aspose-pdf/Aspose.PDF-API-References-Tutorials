---
title: Convert To BMP
linktitle: Convert To BMP
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /net/programming-with-images/convert-to-bmp/
---
### Sample source code for Convert To BMP using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "AddImage.pdf");
            for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
            {
                using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
                {
                    // Create Resolution object
                    Resolution resolution = new Resolution(300);
                    // Create BMP device with specified attributes
                    // Width, Height, Resolution, PageSize
                    BmpDevice bmpDevice = new BmpDevice(resolution);
                    // Convert a particular page and save the image to stream
                    bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
                    // Close stream
                    imageStream.Close();
                }
            } 
            Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```