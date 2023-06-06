---
title: Pages To Images
linktitle: Pages To Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 200
url: /net/programming-with-images/pages-to-images/
---
### Sample source code for Pages To Images using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
            for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
            {
                using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
                {
                    // Create JPEG device with specified attributes
                    // Width, Height, Resolution, Quality
                    // Quality [0-100], 100 is Maximum
                    // Create Resolution object
                    Resolution resolution = new Resolution(300);
                    // JpegDevice jpegDevice = new JpegDevice(500, 700, resolution, 100);
                    JpegDevice jpegDevice = new JpegDevice(resolution, 100);
                    // Convert a particular page and save the image to stream
                    jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
                    // Close stream
                    imageStream.Close();
                }
            }
            System.Console.WriteLine("PDF pages are converted to individual images successfully!");
```