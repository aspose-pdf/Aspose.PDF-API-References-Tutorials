---
title: Get Particular Page
linktitle: Get Particular Page
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /pdf/net/programming-with-pdf-pages/get-particular-page/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument = new Document(dataDir + "GetParticularPage.pdf");

            // Get particular page
            Page pdfPage = pdfDocument.Pages[2];

            // Save the page as PDF file
            Document newDocument = new Document();

            newDocument.Pages.Add(pdfPage);

            dataDir = dataDir + "GetParticularPage_out.pdf";
            newDocument.Save(dataDir);
            
            System.Console.WriteLine("\nParticular page accessed successfully.\nFile saved at " + dataDir);
        
```

