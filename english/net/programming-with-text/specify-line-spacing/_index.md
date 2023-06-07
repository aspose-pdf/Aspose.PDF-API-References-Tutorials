---
title: Specify Line Spacing
linktitle: Specify Line Spacing
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 510
url: /net/programming-with-text/specify-line-spacing/
---
### Sample source code for Specify Line Spacing using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            string fontFile = dataDir + "HPSimplified.TTF";
            // Load input PDF file
            Document doc = new Document();
            //Create TextFormattingOptions with LineSpacingMode.FullSize
            TextFormattingOptions formattingOptions = new TextFormattingOptions();
            formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
            // Create text builder object for first page of document
            //TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
            // Create text fragment with sample string
            TextFragment textFragment = new TextFragment("Hello world");
            if (fontFile != "")
            {
                // Load the TrueType font into stream object
                using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
                {
                    // Set the font name for text string
                    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
                    // Specify the position for Text Fragment
                    textFragment.Position = new Position(100, 600);
                    //Set TextFormattingOptions of current fragment to predefined(which points to LineSpacingMode.FullSize)
                    textFragment.TextState.FormattingOptions = formattingOptions;
                    // Add the text to TextBuilder so that it can be placed over the PDF file
                    //textBuilder.AppendText(textFragment);
                    var page = doc.Pages.Add();
                    page.Paragraphs.Add(textFragment);
                }
                dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
                // Save resulting PDF document
                doc.Save(dataDir);
            }
```