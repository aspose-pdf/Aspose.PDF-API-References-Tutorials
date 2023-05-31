---
title: Change Orientation
linktitle: Change Orientation
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /pdf/net/programming-with-pdf-pages/change-orientation/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            Document doc = new Document(dataDir + "input.pdf");
            foreach (Page page in doc.Pages)
            {
                
                Aspose.Pdf.Rectangle r = page.MediaBox;
                double newHeight = r.Width;
                double newWidth = r.Height;
                double newLLX = r.LLX;
                //  We must to move page upper in order to compensate changing page size
                // (lower edge of the page is 0,0 and information is usually placed from the
                //  Top of the page. That's why we move lover edge upper on difference between
                //  Old and new height.
                double newLLY = r.LLY + (r.Height - newHeight);
                page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
                // Sometimes we also need to set CropBox (if it was set in original file)
                page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);

                // Setting Rotation angle of page
                page.Rotate = Rotation.on90;
            }

            dataDir = dataDir + "ChangeOrientation_out.pdf";
            // Save output file
            doc.Save(dataDir);
            
            System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
        
```

