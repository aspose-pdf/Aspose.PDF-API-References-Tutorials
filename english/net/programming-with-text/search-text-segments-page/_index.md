---
title: Search Text Segments Page
linktitle: Search Text Segments Page
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 470
url: /net/programming-with-text/search-text-segments-page/
---
### Sample source code for Search Text Segments Page using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
            // Create TextAbsorber object to find all instances of the input search phrase
            TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
            // Accept the absorber for all the pages
            pdfDocument.Pages[2].Accept(textFragmentAbsorber);
            // Get the extracted text fragments
            TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
            // Loop through the fragments
            foreach (TextFragment textFragment in textFragmentCollection)
            {
                foreach (TextSegment textSegment in textFragment.Segments)
                {
                    Console.WriteLine("Text : {0} ", textSegment.Text);
                    Console.WriteLine("Position : {0} ", textSegment.Position);
                    Console.WriteLine("XIndent : {0} ",
                    textSegment.Position.XIndent);
                    Console.WriteLine("YIndent : {0} ",
                    textSegment.Position.YIndent);
                    Console.WriteLine("Font - Name : {0}",
                    textSegment.TextState.Font.FontName);
                    Console.WriteLine("Font - IsAccessible : {0} ",
                    textSegment.TextState.Font.IsAccessible);
                    Console.WriteLine("Font - IsEmbedded : {0} ",
                    textSegment.TextState.Font.IsEmbedded);
                    Console.WriteLine("Font - IsSubset : {0} ",
                    textSegment.TextState.Font.IsSubset);
                    Console.WriteLine("Font Size : {0} ",
                    textSegment.TextState.FontSize);
                    Console.WriteLine("Foreground Color : {0} ",
                    textSegment.TextState.ForegroundColor);
                }
            }
```