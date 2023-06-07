---
title: Search Text And Draw Rectangle
linktitle: Search Text And Draw Rectangle
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 460
url: /net/programming-with-text/search-text-and-draw-rectangle/
---
### Sample source code for Search Text And Draw Rectangle using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
            // Create TextAbsorber object to find all the phrases matching the regular expression
            TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
            TextSearchOptions textSearchOptions = new TextSearchOptions(true);
            textAbsorber.TextSearchOptions = textSearchOptions;
            document.Pages.Accept(textAbsorber); 
            var editor = new PdfContentEditor(document); 
            foreach (TextFragment textFragment in textAbsorber.TextFragments)
            {
                foreach (TextSegment textSegment in textFragment.Segments)
                {
                        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
                }
            }
            dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
            document.Save(dataDir);
            Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```