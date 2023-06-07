---
title: Add Text With Shading Colors
linktitle: Add Text With Shading Colors
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /net/programming-with-text/add-text-with-shading-colors/
---
### Sample source code for Add Text With Shading Colors using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
            {
                TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
                pdfDocument.Pages.Accept(absorber);
                TextFragment textFragment = absorber.TextFragments[1];
                // Create new color with pattern colorspace
                textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
                {
                    PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
                };
                textFragment.TextState.Underline = true;
                pdfDocument.Save(dataDir + "text_out.pdf");
            }
```