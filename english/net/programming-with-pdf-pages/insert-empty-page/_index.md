---
title: Insert Empty Page
linktitle: Insert Empty Page
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /pdf/net/programming-with-pdf-pages/insert-empty-page/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument1 = new Document(dataDir + "InsertEmptyPage.pdf");

            // Insert a empty page in a PDF
            pdfDocument1.Pages.Insert(2);
            dataDir = dataDir + "InsertEmptyPage_out.pdf";
            // Save output file
            pdfDocument1.Save(dataDir);
            
            System.Console.WriteLine("\nEmpty page inserted successfully.\nFile saved at " + dataDir);
        
```

