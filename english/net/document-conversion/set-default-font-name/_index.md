---
title: Set Default Font Name
linktitle: Set Default Font Name
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 270
url: /pdf/net/document-conversion/set-default-font-name/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            using (Document pdfDocument = new Document(dataDir + "input.pdf"))
            {
                using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
                {
                    Resolution resolution = new Resolution(300);
                    PngDevice pngDevice = new PngDevice(resolution);
                    RenderingOptions ro = new RenderingOptions();
                    ro.DefaultFontName = "Arial";
                    pngDevice.RenderingOptions = ro;
                    pngDevice.Process(pdfDocument.Pages[1], imageStream);
                }
            }
            

        
```

