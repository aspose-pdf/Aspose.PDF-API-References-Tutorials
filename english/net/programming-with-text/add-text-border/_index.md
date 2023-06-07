---
title: Add Text Border
linktitle: Add Text Border
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /net/programming-with-text/add-text-border/
---
### Sample source code for Add Text Border using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create new document object 
            Document pdfDocument = new Document();
            // Get particular page
            Page pdfPage = (Page)pdfDocument.Pages.Add();
            // Create text fragment
            TextFragment textFragment = new TextFragment("main text");
            textFragment.Position = new Position(100, 600);
            // Set text properties
            textFragment.TextState.FontSize = 12;
            textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
            textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
            // Set StrokingColor property for drawing border (stroking) around text rectangle
            textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
            // Set DrawTextRectangleBorder property value to true
            textFragment.TextState.DrawTextRectangleBorder = true;
            TextBuilder tb = new TextBuilder(pdfPage);
            tb.AppendText(textFragment);
            // Save the document
            pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```