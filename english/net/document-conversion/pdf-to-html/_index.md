---
title: PDF to HTML
linktitle: PDF to HTML
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 130
url: /pdf/net/document-conversion/pdf-to-html/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Open the source PDF document
            Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

            // Save the file into MS document format
            pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
            
        
```

