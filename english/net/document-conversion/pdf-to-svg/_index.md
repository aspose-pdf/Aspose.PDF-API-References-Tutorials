---
title: PDF to SVG
linktitle: PDF to SVG
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 180
url: /pdf/net/document-conversion/pdf-to-svg/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Load PDF document
            Document doc = new Document(dataDir + "input.pdf");
            // Instantiate an object of SvgSaveOptions
            SvgSaveOptions saveOptions = new SvgSaveOptions();
            // Do not compress SVG image to Zip archive
            saveOptions.CompressOutputToZipArchive = false;
            // Save the output in SVG files
            doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
            
        
```

