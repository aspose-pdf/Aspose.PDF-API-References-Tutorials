---
title: Split To Pages
linktitle: Split To Pages
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 140
url: /pdf/net/programming-with-pdf-pages/split-to-pages/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();
            
            // Open document
            Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");

            int pageCount = 1;

            // Loop through all the pages
            foreach (Page pdfPage in pdfDocument.Pages)
            {
                Document newDocument = new Document();
                newDocument.Pages.Add(pdfPage);
                newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
                pageCount++;
            }
            
         
        
```

