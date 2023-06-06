---
title: Page To TIFF
linktitle: Page To TIFF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 230
url: /net/programming-with-images/page-to-tiff/
---
### Sample source code for Page To TIFF using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
            // Create Resolution object
            Resolution resolution = new Resolution(300);
            // Create TiffSettings object
            TiffSettings tiffSettings = new TiffSettings();
            tiffSettings.Compression = CompressionType.None;
            tiffSettings.Depth = ColorDepth.Default;
            tiffSettings.Shape = ShapeType.Landscape;
            tiffSettings.SkipBlankPages = false;
            // Create TIFF device
            TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
            // Convert a particular page and save the image to stream
            tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
            System.Console.WriteLine("PDF one page converted to tiff successfully!");
```