---
title: PDF to EPUB
linktitle: PDF to EPUB
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /pdf/net/document-conversion/pdf-to-epub/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Load PDF document
            Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

            // Instantiate Epub Save options
            EpubSaveOptions options = new EpubSaveOptions();
            
            // Specify the layout for contents
            options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
            
            // Save the ePUB document
            pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
            
        
```

