---
title: Postscript to PDF
linktitle: Postscript to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 230
url: /pdf/net/document-conversion/postscript-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create a new instance of PsLoadOptions
            LoadOptions options = new PsLoadOptions();
            // Open .ps document with created load options
            Document pdfDocument = new Document(dataDir + "input.ps", options);
            // Save document
            pdfDocument.Save(dataDir + "PSToPDF.pdf");
            
        
```

