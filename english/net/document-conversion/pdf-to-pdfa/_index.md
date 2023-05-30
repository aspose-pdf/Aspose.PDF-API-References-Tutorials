---
title: PDF to PDFA
linktitle: PDF to PDFA
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 140
url: /pdf/net/document-conversion/pdf-to-pdfa/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Open document
            Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
            
            // Convert to PDF/A compliant document
            // During conversion process, the validation is also performed
            pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

            dataDir = dataDir + "PDFToPDFA_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            
            Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
        
```

