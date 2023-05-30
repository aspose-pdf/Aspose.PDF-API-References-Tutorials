---
title: PDF to PPT
linktitle: PDF to PPT
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 170
url: /pdf/net/document-conversion/pdf-to-ppt/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Load PDF document
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "input.pdf");
            // Instantiate PptxSaveOptions instance
            Aspose.Pdf.PptxSaveOptions pptx_save = new Aspose.Pdf.PptxSaveOptions();
            // Save the output in PPTX format
            doc.Save(dataDir + "PDFToPPT_out.pptx", pptx_save);
            
        
```

