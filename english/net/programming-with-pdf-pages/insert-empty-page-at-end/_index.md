---
title: Insert Empty Page At End
linktitle: Insert Empty Page At End
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 130
url: /pdf/net/programming-with-pdf-pages/insert-empty-page-at-end/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");

            // Insert an empty page at the end of a PDF file
            pdfDocument1.Pages.Add();

            dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
            // Save output file
            pdfDocument1.Save(dataDir);
            
            System.Console.WriteLine("\nEmpty page inserted successfully at the end of document.\nFile saved at " + dataDir);

        
```

