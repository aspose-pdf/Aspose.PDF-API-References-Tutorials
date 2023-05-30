---
title: SVG to PDF
linktitle: SVG to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 280
url: /pdf/net/document-conversion/svg-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instantiate LoadOption object using SVG load option
            Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

            // Create Document object
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

            // Save the resultant PDF document
            doc.Save(dataDir + "SVGToPDF_out.pdf");
            
        
```

