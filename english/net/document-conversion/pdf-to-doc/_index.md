---
title: PDF to DOC
linktitle: PDF to DOC
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /pdf/net/document-conversion/pdf-to-doc/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";          
            
            // Open the source PDF document
            Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");

            // Save the file into MS document format
            pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
            
            
        
```

