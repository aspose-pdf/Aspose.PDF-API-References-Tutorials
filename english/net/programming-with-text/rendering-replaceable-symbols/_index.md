---
title: Rendering Replaceable Symbols
linktitle: Rendering Replaceable Symbols
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 310
url: /net/programming-with-text/rendering-replaceable-symbols/
---
### Sample source code for Rendering Replaceable Symbols using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
            Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
            // Initialize new TextFragment with text containing required newline markers
            Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
            // Set text fragment properties if necessary
            textFragment.TextState.FontSize = 12;
            textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
            textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
            textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
            // Create TextParagraph object
            TextParagraph par = new TextParagraph();
            // Add new TextFragment to paragraph
            par.AppendLine(textFragment);
            // Set paragraph position
            par.Position = new Aspose.Pdf.Text.Position(100, 600);
            // Create TextBuilder object
            TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
            // Add the TextParagraph using TextBuilder
            textBuilder.AppendParagraph(par);
            dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
            pdfApplicationDoc.Save(dataDir);
            Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```