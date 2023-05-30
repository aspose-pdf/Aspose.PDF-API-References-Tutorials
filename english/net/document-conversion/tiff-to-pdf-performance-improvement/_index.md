---
title: TIFF to PDF Performance Improvement
linktitle: TIFF to PDF Performance Improvement
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 310
url: /pdf/net/document-conversion/tiff-to-pdf-performance-improvement/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Get a list of tiff image files
            string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

            // Instantiate a Document object
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Navigate through the files and them in the pdf file
            foreach (string myFile in files)
            {

                // Load all tiff files in byte array
                FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
                byte[] tmpBytes = new byte[fs.Length];
                fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

                MemoryStream mystream = new MemoryStream(tmpBytes);
                Bitmap b = new Bitmap(mystream);
                // Create a new Page in the Pdf document
                Aspose.Pdf.Page currpage = doc.Pages.Add();

                // Set margins so image will fit, etc.
                currpage.PageInfo.Margin.Top = 5;
                currpage.PageInfo.Margin.Bottom = 5;
                currpage.PageInfo.Margin.Left = 5;
                currpage.PageInfo.Margin.Right = 5;

                currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
                currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

                // Create an image object
                Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

                // Add the image into paragraphs collection of the page
                currpage.Paragraphs.Add(image1);

                // Set IsBlackWhite property to true for performance improvement
                image1.IsBlackWhite = true;
                // Set the ImageStream to a MemoryStream object
                image1.ImageStream = mystream;
                // Set desired image scale
                image1.ImageScale = 0.95F;
            }

            // Save the Pdf
            doc.Save(dataDir + "PerformaceImprovement_out.pdf");
            
        
```

