---
title: Page Orientation According Image Dimensions
linktitle: Page Orientation According Image Dimensions
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /pdf/net/document-conversion/page-orientation-according-image-dimensions/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Retrieve names of all the JPG files in a particular Directory
            string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

            int counter;
            for (counter = 0; counter < fileEntries.Length - 1; counter++)
            {
                // Create a page object
                Aspose.Pdf.Page page = doc.Pages.Add();

                // Creat an image object
                Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
                image1.File = fileEntries[counter];

                // Create a BitMap object in order to get the information of image file
                Bitmap myimage = new Bitmap(fileEntries[counter]);
                // Check if the width of the image file is greater than Page width or not
                if (myimage.Width > page.PageInfo.Width)
                    // If the Image width is greater than page width, then set the page orientation to Landscape
                    page.PageInfo.IsLandscape = true;
                else
                    // If the Image width is less than page width, then set the page orientation to Portrait
                    page.PageInfo.IsLandscape = false;
                // Add the image to paragraphs collection of the PDF document 
                page.Paragraphs.Add(image1);
            }
            // Save the Pdf file
            doc.Save(dataDir + "SetPageOrientation_out.pdf");
            
        
```

