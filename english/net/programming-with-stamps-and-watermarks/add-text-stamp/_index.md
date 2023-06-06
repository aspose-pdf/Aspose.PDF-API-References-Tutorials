---
title: Add Text Stamp
linktitle: Add Text Stamp
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /net/programming-with-stamps-and-watermarks/add-text-stamp/
---
### Sample source code for Add Text Stamp using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
            // Create text stamp
            TextStamp textStamp = new TextStamp("Sample Stamp");
            // Set whether stamp is background
            textStamp.Background = true;
            // Set origin
            textStamp.XIndent = 100;
            textStamp.YIndent = 100;
            // Rotate stamp
            textStamp.Rotate = Rotation.on90;
            // Set text properties
            textStamp.TextState.Font = FontRepository.FindFont("Arial");
            textStamp.TextState.FontSize = 14.0F;
            textStamp.TextState.FontStyle = FontStyles.Bold;
            textStamp.TextState.FontStyle = FontStyles.Italic;
            textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
            // Add stamp to particular page
            pdfDocument.Pages[1].AddStamp(textStamp);
            dataDir = dataDir + "AddTextStamp_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            
```