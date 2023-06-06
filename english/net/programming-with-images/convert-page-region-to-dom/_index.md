---
title: Convert Page Region To DOM
linktitle: Convert Page Region To DOM
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /net/programming-with-images/convert-page-region-to-dom/
---
### Sample source code for Convert Page Region To DOM using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document document = new Document( dataDir + "AddImage.pdf");
            // Get rectangle of particular page region
            Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
            // Set CropBox value as per rectangle of desired page region
            document.Pages[1].CropBox = pageRect;
            // Save cropped document into stream
            MemoryStream ms = new MemoryStream();
            document.Save(ms);
            // Open cropped PDF document and convert to image
            document = new Document(ms);
            // Create Resolution object
            Resolution resolution = new Resolution(300);
            // Create PNG device with specified attributes
            PngDevice pngDevice = new PngDevice(resolution);
            dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
            // Convert a particular page and save the image to stream
            pngDevice.Process(document.Pages[1], dataDir);
            ms.Close();
            Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```