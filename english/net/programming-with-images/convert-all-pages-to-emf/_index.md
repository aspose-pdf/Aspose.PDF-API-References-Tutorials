---
title: Convert All Pages To EMF
linktitle: Convert All Pages To EMF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /net/programming-with-images/convert-all-pages-to-emf/
---
### Sample source code for Convert All Pages To EMF using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
            for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
            {
                using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
                {
                    // Create Resolution object
                    Resolution resolution = new Resolution(300);
                    // Create PNG device with specified attributes
                    // Width, Height, Resolution
                    EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
                    // Convert a particular page and save the image to stream
                    emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
                    // Close stream
                    imageStream.Close();
                }
            }
            System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```