---
title: MHT to PDF
linktitle: MHT to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /pdf/net/document-conversion/mht-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            MhtLoadOptions options = new MhtLoadOptions();
            // Load document
            Document document = new Document(dataDir  + "test.mht", options);
            // Save the output as PDF document
            document.Save(dataDir + "MHTToPDF_out.pdf");
            
        
```

