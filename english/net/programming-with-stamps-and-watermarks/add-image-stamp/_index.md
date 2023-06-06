---
title: Add Image Stamp
linktitle: Add Image Stamp
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /net/programming-with-stamps-and-watermarks/add-image-stamp/
---
### Sample source code for Add Image Stamp using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");
            // Create image stamp
            ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
            imageStamp.Background = true;
            imageStamp.XIndent = 100;
            imageStamp.YIndent = 100;
            imageStamp.Height = 300;
            imageStamp.Width = 300;
            imageStamp.Rotate = Rotation.on270;
            imageStamp.Opacity = 0.5;
            // Add stamp to particular page
            pdfDocument.Pages[1].AddStamp(imageStamp);
            dataDir = dataDir + "AddImageStamp_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```