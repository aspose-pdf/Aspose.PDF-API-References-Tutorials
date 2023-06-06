---
title: Store Image In XImage Collection
linktitle: Store Image In XImage Collection
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 290
url: /net/programming-with-images/store-image-in-ximage-collection/
---
### Sample source code for Store Image In XImage Collection using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Initialize Document
            Aspose.Pdf.Document document = new Document();
            document.Pages.Add();
            Page page = document.Pages[1];
            FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
            page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
            XImage ximage = page.Resources.Images[page.Resources.Images.Count];
            page.Contents.Add(new GSave());
            // Set coordinates
            int lowerLeftX = 0;
            int lowerLeftY = 0;
            int upperRightX = 600;
            int upperRightY = 600;
            Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
            Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
            // Using ConcatenateMatrix (concatenate matrix) operator: defines how image must be placed
            page.Contents.Add(new ConcatenateMatrix(matrix));
            page.Contents.Add(new Do(ximage.Name));
            page.Contents.Add(new GRestore());
            document.Save(dataDir + "FlateDecodeCompression.pdf");
```