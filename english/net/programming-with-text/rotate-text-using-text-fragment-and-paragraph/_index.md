---
title: Rotate Text Using Text Fragment And Paragraph
linktitle: Rotate Text Using Text Fragment And Paragraph
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 400
url: /net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
### Sample source code for Rotate Text Using Text Fragment And Paragraph using Aspose.PDF for .NET 
```csharp
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Initialize document object
            Document pdfDocument = new Document();
            // Get particular page
            Page pdfPage = (Page)pdfDocument.Pages.Add();
            // Create text fragment
            TextFragment textFragment1 = new TextFragment("main text");
            // Set text properties
            textFragment1.TextState.FontSize = 12;
            textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            // Create text fragment
            TextFragment textFragment2 = new TextFragment("rotated text");
            // Set text properties
            textFragment2.TextState.FontSize = 12;
            textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            // Set rotation
            textFragment2.TextState.Rotation = 315;
            // Create text fragment
            TextFragment textFragment3 = new TextFragment("rotated text");
            // Set text properties
            textFragment3.TextState.FontSize = 12;
            textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            // Set rotation
            textFragment3.TextState.Rotation = 270;
            pdfPage.Paragraphs.Add(textFragment1);
            pdfPage.Paragraphs.Add(textFragment2);
            pdfPage.Paragraphs.Add(textFragment3);
            // Save document
            pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```