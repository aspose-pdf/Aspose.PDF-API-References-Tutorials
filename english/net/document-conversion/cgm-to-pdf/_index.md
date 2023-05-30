---
title: CGM to PDF
linktitle: CGM to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /pdf/net/document-conversion/cgm-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instantiate LoadOption object using CGMLoadOption
            Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
            // Instantiate Document object
            Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
            // Save the resultant PDF document
            doc.Save(dataDir+ "TECHDRAW_out.pdf");
            
        
```

