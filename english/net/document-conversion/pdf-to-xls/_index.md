---
title: PDF to XLS
linktitle: PDF to XLS
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 200
url: /pdf/net/document-conversion/pdf-to-xls/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Load PDF document
            Document pdfDocument = new Document(dataDir + "input.pdf");

            // Instantiate ExcelSave Option object
            Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

            // Save the output in XLS format
            pdfDocument.Save("PDFToXLS_out.xls", excelsave);
            
        
```

