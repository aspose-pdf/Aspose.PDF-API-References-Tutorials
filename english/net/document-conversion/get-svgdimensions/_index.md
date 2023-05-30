---
title: Get SVGDimensions
linktitle: Get SVGDimensions
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /pdf/net/document-conversion/get-svgdimensions/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            
            var loadopt = new SvgLoadOptions();
            loadopt.AdjustPageSize = true;
            var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
            svgDoc.Pages[1].PageInfo.Margin.Top = 0;
            svgDoc.Pages[1].PageInfo.Margin.Left = 0;
            svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
            svgDoc.Pages[1].PageInfo.Margin.Right = 0;
            svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
            
        
```

