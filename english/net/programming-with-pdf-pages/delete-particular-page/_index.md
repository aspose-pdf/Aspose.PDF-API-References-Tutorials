---
title: Delete Particular Page
linktitle: Delete Particular Page
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /pdf/net/programming-with-pdf-pages/delete-particular-page/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument = new Document(dataDir + "DeleteParticularPage.pdf");

            // Delete a particular page
            pdfDocument.Pages.Delete(2);

            dataDir = dataDir + "DeleteParticularPage_out.pdf";
            // Save updated PDF
            pdfDocument.Save(dataDir);
            
            System.Console.WriteLine("\nParticular page deleted successfully.\nFile saved at " + dataDir);
        
```

