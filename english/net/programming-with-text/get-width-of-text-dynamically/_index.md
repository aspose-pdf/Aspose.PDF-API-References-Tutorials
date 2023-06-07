---
title: Get Width Of Text Dynamically
linktitle: Get Width Of Text Dynamically
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 220
url: /net/programming-with-text/get-width-of-text-dynamically/
---
### Sample source code for Get Width Of Text Dynamically using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
            TextState ts = new TextState();
            ts.Font = font;
            ts.FontSize = 14;
            if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
                Console.WriteLine("Unexpected font string measure!");
            if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
                Console.WriteLine("Unexpected font string measure!");
            for (char c = 'A'; c <= 'z'; c++)
            {
                double fnMeasure = font.MeasureString(c.ToString(), 14);
                double tsMeasure = ts.MeasureString(c.ToString());
                if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
                    Console.WriteLine("Font and state string measuring doesn't match!");
            }
```