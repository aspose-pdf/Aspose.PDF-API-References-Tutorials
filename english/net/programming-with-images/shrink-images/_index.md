---
title: Shrink Images
linktitle: Shrink Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 280
url: /net/programming-with-images/shrink-images/
---
### Sample source code for Shrink Images using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
            // Initialize OptimizationOptions
            var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
            // Set CompressImages option
            optimizeOptions.ImageCompressionOptions.CompressImages = true;
            // Set ImageQuality option
            optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
            // Optimize PDF document using OptimizationOptions
            pdfDocument.OptimizeResources(optimizeOptions);
            dataDir = dataDir + "Shrinkimage_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```