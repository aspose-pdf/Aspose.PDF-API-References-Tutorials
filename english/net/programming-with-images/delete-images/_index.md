---
title: Delete Images
linktitle: Delete Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /net/programming-with-images/delete-images/
---
### Sample source code for Delete Images using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
            // Delete a particular image
            pdfDocument.Pages[1].Resources.Images.Delete(1);
            dataDir = dataDir + "DeleteImages_out.pdf";
            // Save updated PDF file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```