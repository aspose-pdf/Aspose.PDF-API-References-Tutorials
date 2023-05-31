---
title: Update Dimensions
linktitle: Update Dimensions
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 150
url: /pdf/net/programming-with-pdf-pages/update-dimensions/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Open document
            Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");

            // Get page collection
            PageCollection pageCollection = pdfDocument.Pages;

            // Get particular page
            Page pdfPage = pageCollection[1];

            // Set the page size as A4 (11.7 x 8.3 in) and in Aspose.Pdf, 1 inch = 72 points
            // So A4 dimensions in points will be (842.4, 597.6)
            pdfPage.SetPageSize(597.6, 842.4);

            dataDir = dataDir + "UpdateDimensions_out.pdf";
            // Save the updated document
            pdfDocument.Save(dataDir);
            
            System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

        
```

