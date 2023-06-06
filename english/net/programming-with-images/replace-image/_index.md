---
title: Replace Image
linktitle: Replace Image
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 240
url: /net/programming-with-images/replace-image/
---
### Sample source code for Replace Image using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "ReplaceImage.pdf");
            // Replace a particular image
            pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
            dataDir = dataDir + "ReplaceImage_out.pdf";
            // Save updated PDF file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImage replaced successfully.\nFile saved at " + dataDir); 
```