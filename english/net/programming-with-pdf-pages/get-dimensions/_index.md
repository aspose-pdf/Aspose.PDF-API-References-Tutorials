---
title: Get Dimensions
linktitle: Get Dimensions
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /pdf/net/programming-with-pdf-pages/get-dimensions/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");

            // Adds a blank page to pdf document
            Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
            // Get page height and width information
            Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
            // Rotate page at 90 degree angle
            page.Rotate = Rotation.on90;
            // Get page height and width information
            Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
            
        
```

