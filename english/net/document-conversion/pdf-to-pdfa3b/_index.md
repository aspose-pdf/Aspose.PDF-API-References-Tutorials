---
title: PDF to PDFA3b
linktitle: PDF to PDFA3b
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 150
url: /pdf/net/document-conversion/pdf-to-pdfa3b/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Open document
            Document pdfDocument = new Document(dataDir + "input.pdf");            
            
            pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

            dataDir = dataDir + "PDFToPDFA3b_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            
            Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
        
```

