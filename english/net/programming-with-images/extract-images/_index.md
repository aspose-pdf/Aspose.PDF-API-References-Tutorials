---
title: Extract Images
linktitle: Extract Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /net/programming-with-images/extract-images/
---
### Sample source code for Extract Images using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
            // Extract a particular image
            XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
            FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
            // Save output image
            xImage.Save(outputImage, ImageFormat.Jpeg);
            outputImage.Close();
            dataDir = dataDir + "ExtractImages_out.pdf";
            // Save updated PDF file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```