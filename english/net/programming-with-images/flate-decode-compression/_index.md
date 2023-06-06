---
title: Flate Decode Compression
linktitle: Flate Decode Compression
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 140
url: /net/programming-with-images/flate-decode-compression/
---
### Sample source code for Flate Decode Compression using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open Document
            Document doc = new Document(dataDir + "AddImage.pdf");
            // Initialize OptimizationOptions  
            var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
            // To optimise image using FlateDecode Compression set optimization options to Flate
            optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
            // Set Optimization Options 
            doc.OptimizeResources(optimizationOptions);
            // Save Document
            doc.Save(dataDir + "FlateDecodeCompression.pdf");
```