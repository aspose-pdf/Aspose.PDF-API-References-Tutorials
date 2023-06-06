---
title: Large CGMImage to PDF
linktitle: Large CGMImage to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 190
url: /net/programming-with-images/large-cgmimage-to-pdf/
---
### Sample source code for Large CGMImage to PDF using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inputFile = dataDir + "corvette.cgm";
            dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
            // Create an instance of CgmImportOptions
            CgmImportOptions options = new CgmImportOptions();
            // Specify the dimentions for page size import 
            options.PageSize = new SizeF(1000, 1000);
            // Save CGM into PDF format
            PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
            Console.WriteLine("\nLarge CGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```