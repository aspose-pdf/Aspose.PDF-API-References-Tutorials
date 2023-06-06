---
title: Page To EMF
linktitle: Page To EMF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 210
url: /net/programming-with-images/page-to-emf/
---
### Sample source code for Page To EMF using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "PageToEMF.pdf");
            using (FileStream imageStream = new FileStream(dataDir + "image_out.emf", FileMode.Create))
            {
                // Create Resolution object
                Resolution resolution = new Resolution(300);
                // Create EMF device with specified attributes
                // Width, Height, Resolution
                EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
                // Convert a particular page and save the image to stream
                emfDevice.Process(pdfDocument.Pages[1], imageStream);
                // Close stream
                imageStream.Close();
            }
            System.Console.WriteLine("PDF page is converted to EMF successfully!");
```