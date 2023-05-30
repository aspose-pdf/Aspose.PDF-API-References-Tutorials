---
title: PDF to XPS
linktitle: PDF to XPS
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 220
url: /pdf/net/document-conversion/pdf-to-xps/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Load PDF document
            Document pdfDocument = new Document(dataDir + "input.pdf");

            // Instantiate XPS Save options
            Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
            
            // Save the XPS document
            pdfDocument.Save("PDFToXPS_out.xps", saveOptions);       
            
        
```

