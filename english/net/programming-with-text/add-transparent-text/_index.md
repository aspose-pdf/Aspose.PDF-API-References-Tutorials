---
title: Add Transparent Text
linktitle: Add Transparent Text
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /net/programming-with-text/add-transparent-text/
---
### Sample source code for Add Transparent Text using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create Document instance
            Document doc = new Document();
            // Create page to pages collection of PDF file
            Aspose.Pdf.Page page = doc.Pages.Add();
            // Create Graph object 
            Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
            // Create rectangle instance with certain dimensions
            Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
            // Create color object from Alpha color channel
            rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
            // Add rectanlge to shapes collection of Graph object
            canvas.Shapes.Add(rect);
            // Add graph object to paragraphs collection of page object
            page.Paragraphs.Add(canvas);
            // Set value to not change position for graph object
            canvas.IsChangePosition = false;
            // Create TextFragment instance with sample value
            TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
            // Create color object from Alpha channel
            Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
            // Set color information for text instance
            text.TextState.ForegroundColor = color;
            // Add text to paragraphs collection of page instance
            page.Paragraphs.Add(text);
            dataDir = dataDir + "AddTransparentText_out.pdf";
            doc.Save(dataDir);
            Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```