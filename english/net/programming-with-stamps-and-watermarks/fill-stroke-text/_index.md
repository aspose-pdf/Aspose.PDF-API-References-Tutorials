---
title: Fill Stroke Text
linktitle: Fill Stroke Text
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
### Sample source code for Fill Stroke Text using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create TextState object to transfer advanced properties
            TextState ts = new TextState();
            // Set color for stroke
            ts.StrokingColor = Color.Gray;
            // Set text rendering mode
            ts.RenderingMode = TextRenderingMode.StrokeText;
            // Load an input PDF document
            Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
            Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
            stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
            // Bind TextState
            stamp.BindTextState(ts);
            // Set X,Y origin
            stamp.SetOrigin(100, 100);
            stamp.Opacity = 5;
            stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
            stamp.Rotation = 45.0F;
            stamp.IsBackground = false;
            // Add Stamp
            fileStamp.AddStamp(stamp);
            fileStamp.Save(dataDir + "ouput_out.pdf");
            fileStamp.Close();
```