---
title: CGMImage to PDF
linktitle: CGMImage to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/programming-with-images/cgmimage-to-pdf/
---
### Sample source code for CGMImage to PDF using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inputFile = dataDir + "corvette.cgm";
            dataDir = dataDir + "CGMImageToPDF_out.pdf";
            // Save CGM into PDF format
            PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
            Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```