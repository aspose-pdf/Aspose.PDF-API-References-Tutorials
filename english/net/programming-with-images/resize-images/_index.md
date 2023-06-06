---
title: Resize Images
linktitle: Resize Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 250
url: /net/programming-with-images/resize-images/
---
### Sample source code for Resize Images using Aspose.Words for .NET 
```csharp
            // Initialize Time
            var time = DateTime.Now.Ticks;
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
            // Initialize OptimizationOptions
            var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            // Set CompressImages option            optimizeOptions.ImageCompressionOptions.CompressImages = true;            // Set ImageQuality option             optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            // Set ResizeImage option            optimizeOptions.ImageCompressionOptions.ResizeImages = true;            // Set MaxResolution option            optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
            // Optimize PDF document using OptimizationOptions
            pdfDocument.OptimizeResources(optimizeOptions);
            dataDir = dataDir + "ResizeImages_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```