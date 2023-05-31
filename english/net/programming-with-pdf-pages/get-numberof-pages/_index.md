---
title: Get Numberof Pages
linktitle: Get Numberof Pages
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /pdf/net/programming-with-pdf-pages/get-numberof-pages/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");

            // Get page count
            System.Console.WriteLine("Page Count : {0}", pdfDocument.Pages.Count);
            
        
```

