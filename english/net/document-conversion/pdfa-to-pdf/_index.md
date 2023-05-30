---
title: PDFA to PDF
linktitle: PDFA to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /pdf/net/document-conversion/pdfa-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Open document
            Document doc = new Document(dataDir + "PDFAToPDF.pdf");

            // Remove PDF/A compliance information
            doc.RemovePdfaCompliance();
            // Save updated document 
            doc.Save(dataDir + "PDFAToPDF_out.pdf");
            
            
        
```

