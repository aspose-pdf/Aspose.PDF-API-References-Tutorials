---
title: Fast Shrink Images
linktitle: Fast Shrink Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 130
url: /net/programming-with-images/fast-shrink-images/
---
### Sample source code for Fast Shrink Images using Aspose.PDF for .NET 
```csharp
            // Initialize Time
            var time = DateTime.Now.Ticks;
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
            // Initialize OptimizationOptions
            var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
            // Set CompressImages option
            optimizeOptions.ImageCompressionOptions.CompressImages = true;
            // Set ImageQuality option
            optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
            // Set Imagae Compression Version to fast 
            optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
            // Optimize PDF document using OptimizationOptions
            pdfDocument.OptimizeResources(optimizeOptions);
            dataDir = dataDir + "FastShrinkImages_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
            Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```