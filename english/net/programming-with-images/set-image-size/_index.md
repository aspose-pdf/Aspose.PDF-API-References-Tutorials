---
title: Set Image Size
linktitle: Set Image Size
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 270
url: /net/programming-with-images/set-image-size/
---
### Sample source code for Set Image Size using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate Document object
            Document doc = new Document();
            // add page to pages collection of PDF file
            Aspose.Pdf.Page page = doc.Pages.Add();
            // Create an image instance
            Aspose.Pdf.Image img = new Aspose.Pdf.Image();
            // Set Image Width and Height in Points
            img.FixWidth = 100;
            img.FixHeight = 100;
            // Set image type as SVG
            img.FileType = Aspose.Pdf.ImageFileType.Unknown;
            // Path for source file
            img.File = dataDir + "aspose-logo.jpg";
            page.Paragraphs.Add(img);
            //Set page properties
            page.PageInfo.Width = 800;
            page.PageInfo.Height = 800;
            dataDir = dataDir + "SetImageSize_out.pdf";
            // save resultant PDF file
            doc.Save(dataDir);
            Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```