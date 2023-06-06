---
title: Add PDFPage Stamp
linktitle: Add PDFPage Stamp
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/programming-with-stamps-and-watermarks/add-pdfpage-stamp/
---
### Sample source code for Add PDFPage Stamp using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");
            // Create page stamp
            PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
            pageStamp.Background = true;
            pageStamp.XIndent = 100;
            pageStamp.YIndent = 100;
            pageStamp.Rotate = Rotation.on180;
            // Add stamp to particular page
            pdfDocument.Pages[1].AddStamp(pageStamp);
            dataDir = dataDir + "PDFPageStamp_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);
```