---
title: Concatenate Pdf Files
linktitle: Concatenate Pdf Files
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /pdf/net/programming-with-pdf-pages/concatenate-pdf-files/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open first document
            Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
            // Open second document
            Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");

            // Add pages of second document to the first
            pdfDocument1.Pages.Add(pdfDocument2.Pages);

            dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
            // Save concatenated output file
            pdfDocument1.Save(dataDir);
            
            System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);
        
```

