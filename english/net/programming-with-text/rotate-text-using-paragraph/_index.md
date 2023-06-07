---
title: Rotate Text Using Paragraph
linktitle: Rotate Text Using Paragraph
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 380
url: /net/programming-with-text/rotate-text-using-paragraph/
---
### Sample source code for Rotate Text Using Paragraph using Aspose.PDF for .NET 
```csharp
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Initialize document object
            Document pdfDocument = new Document();
            // Get particular page
            Page pdfPage = (Page)pdfDocument.Pages.Add();
            TextParagraph paragraph = new TextParagraph();
            paragraph.Position = new Position(200, 600);
            // Create text fragment
            TextFragment textFragment1 = new TextFragment("rotated text");
            // Set text properties
            textFragment1.TextState.FontSize = 12;
            textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            // Set rotation
            textFragment1.TextState.Rotation = 45;
            // Create text fragment
            TextFragment textFragment2 = new TextFragment("main text");
            // Set text properties
            textFragment2.TextState.FontSize = 12;
            textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            // Create text fragment
            TextFragment textFragment3 = new TextFragment("another rotated text");
            // Set text properties
            textFragment3.TextState.FontSize = 12;
            textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
            // Set rotation
            textFragment3.TextState.Rotation = -45;
            // Append the text fragments to the paragraph
            paragraph.AppendLine(textFragment1);
            paragraph.AppendLine(textFragment2);
            paragraph.AppendLine(textFragment3);
            // Create TextBuilder object
            TextBuilder textBuilder = new TextBuilder(pdfPage);
            // Append the text paragraph to the PDF page
            textBuilder.AppendParagraph(paragraph);
            // Save document
            pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```