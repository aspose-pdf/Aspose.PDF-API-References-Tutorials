---
title: EPUB to PDF
linktitle: EPUB to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /pdf/net/document-conversion/epub-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";

                // Instantiate LoadOption object using EPUB load option
                EpubLoadOptions epubload = new EpubLoadOptions();

                // Create Document object
                Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

                // Save the resultant PDF document
                pdf.Save(dataDir + "EPUBToPDF_out.pdf");
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

