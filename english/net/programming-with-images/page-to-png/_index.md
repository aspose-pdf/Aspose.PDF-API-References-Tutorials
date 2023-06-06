---
title: Page To PNG
linktitle: Page To PNG
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 220
url: /net/programming-with-images/page-to-png/
---
### Sample source code for Page To PNG using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
            using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
            {
                // Create Resolution object
                Resolution resolution = new Resolution(300);
                // Create PNG device with specified attributes (Width, Height, Resolution)
                PngDevice pngDevice = new PngDevice(resolution);
                // Convert a particular page and save the image to stream
                pngDevice.Process(pdfDocument.Pages[1], imageStream);
                // Close stream
                imageStream.Close();
            }
```