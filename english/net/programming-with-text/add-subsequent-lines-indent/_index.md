---
title: Add Subsequent Lines Indent
linktitle: Add Subsequent Lines Indent
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /net/programming-with-text/add-subsequent-lines-indent/
---
### Sample source code for Add Subsequent Lines Indent using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create new document object 
            Aspose.Pdf.Document document = new Aspose.Pdf.Document();
            Aspose.Pdf.Page page = document.Pages.Add();
            Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
            // Initilize TextFormattingOptions for the text fragment and specify SubsequentLinesIndent value
            text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
            {
                SubsequentLinesIndent = 20
            };
            page.Paragraphs.Add(text);
            text = new Aspose.Pdf.Text.TextFragment("Line2");
            page.Paragraphs.Add(text);
            text = new Aspose.Pdf.Text.TextFragment("Line3");
            page.Paragraphs.Add(text);
            text = new Aspose.Pdf.Text.TextFragment("Line4");
            page.Paragraphs.Add(text);
            text = new Aspose.Pdf.Text.TextFragment("Line5");
            page.Paragraphs.Add(text);
            document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```