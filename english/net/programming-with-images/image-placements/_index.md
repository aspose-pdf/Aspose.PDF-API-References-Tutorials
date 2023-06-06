---
title: Image Placements
linktitle: Image Placements
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 170
url: /net/programming-with-images/image-placements/
---
### Sample source code for Image Placements using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Load the source PDF document
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
            ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
            // Load the contents of first page
            doc.Pages[1].Accept(abs);
            foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
            {
                // Get image properties
                Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
                Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
                Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
                Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
                Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
                Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
                // Retrieve image with visible dimensions
                Bitmap scaledImage;
                using (MemoryStream imageStream = new MemoryStream())
                {
                    // Retrieve image from resources
                    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
                    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
                    // Create bitmap with actual dimensions
                    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
                }
            }
```