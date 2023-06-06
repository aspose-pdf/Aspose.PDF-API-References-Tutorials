---
title: Bradley Algorithm
linktitle: Bradley Algorithm
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /net/programming-with-images/bradley-algorithm/
---
### Sample source code for Bradley Algorithm using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
            string outputImageFile = dataDir + "resultant_out.tif";
            string outputBinImageFile = dataDir + "37116-bin_out.tif";
            // Create Resolution object
            Resolution resolution = new Resolution(300);
            // Create TiffSettings object
            TiffSettings tiffSettings = new TiffSettings();
            tiffSettings.Compression = CompressionType.LZW;
            tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
            // Create TIFF device
            TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
            // Convert a particular page and save the image to stream
            tiffDevice.Process(pdfDocument, outputImageFile);
            using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
            {
                using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
                {
                    tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
                }
            }
            System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```