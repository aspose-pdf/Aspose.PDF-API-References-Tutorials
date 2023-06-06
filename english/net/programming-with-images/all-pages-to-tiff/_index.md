---
title: All Pages To TIFF
linktitle: All Pages To TIFF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /net/programming-with-images/all-pages-to-tiff/
---
### Sample source code for All Pages To TIFF using Aspose.PDF for .NET 
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
            tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
            System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```