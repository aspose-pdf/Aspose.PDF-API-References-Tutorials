---
title: Image to PDF
linktitle: Image to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 180
url: /net/programming-with-images/image-to-pdf/
---
### Sample source code for Image to PDF using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate Document Object
            Document doc = new Document();
            // Add a page to pages collection of document
            Page page = doc.Pages.Add();
            // Load the source image file to Stream object
            FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
            byte[] tmpBytes = new byte[fs.Length];
            fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
            MemoryStream mystream = new MemoryStream(tmpBytes);
            // Instantiate BitMap object with loaded image stream
            Bitmap b = new Bitmap(mystream);
            // Set margins so image will fit, etc.
            page.PageInfo.Margin.Bottom = 0;
            page.PageInfo.Margin.Top = 0;
            page.PageInfo.Margin.Left = 0;
            page.PageInfo.Margin.Right = 0;
            page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
            // Create an image object
            Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
            // Add the image into paragraphs collection of the section
            page.Paragraphs.Add(image1);
            // Set the image file stream
            image1.ImageStream = mystream;
            dataDir = dataDir + "ImageToPDF_out.pdf";
            // Save resultant PDF file
            doc.Save(dataDir);
            // Close memoryStream object
            mystream.Close();
            Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```