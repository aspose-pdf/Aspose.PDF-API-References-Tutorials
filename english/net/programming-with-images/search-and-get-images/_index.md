---
title: Search And Get Images
linktitle: Search And Get Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 260
url: /net/programming-with-images/search-and-get-images/
---
### Sample source code for Search And Get Images using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
            // Create ImagePlacementAbsorber object to perform image placement search
            ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
            // Accept the absorber for all the pages
            doc.Pages.Accept(abs);
            // Loop through all ImagePlacements, get image and ImagePlacement Properties
            foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
            {
                // Get the image using ImagePlacement object
                XImage image = imagePlacement.Image;
                // Display image placement properties for all placements
                Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
                Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
                Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
                Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
                Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
                Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
            }
```