---
title: Search And Get Text Page
linktitle: Search And Get Text Page
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 430
url: /net/programming-with-text/search-and-get-text-page/
---
### Sample source code for Search And Get Text Page using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
            // Create TextAbsorber object to find all instances of the input search phrase
            TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
            // Accept the absorber for all the pages
            pdfDocument.Pages.Accept(textFragmentAbsorber);
            // Get the extracted text fragments
            TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
            // Loop through the fragments
            foreach (TextFragment textFragment in textFragmentCollection)
            {
                foreach (TextSegment textSegment in textFragment.Segments)
                {
                    Console.WriteLine("Text : {0} ", textSegment.Text);
                    Console.WriteLine("Position : {0} ", textSegment.Position);
                    Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
                    Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
                    Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
                    Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
                    Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
                    Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
                    Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
                    Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
                }
            }
```