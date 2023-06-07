---
title: Search And Get Text All
linktitle: Search And Get Text All
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 420
url: /net/programming-with-text/search-and-get-text-all/
---
### Sample source code for Search And Get Text All using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
            // Create TextAbsorber object to find all instances of the input search phrase
            TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
            // Accept the absorber for all the pages
            pdfDocument.Pages.Accept(textFragmentAbsorber);
            // Get the extracted text fragments
            TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
            // Loop through the fragments
            foreach (TextFragment textFragment in textFragmentCollection)
            {
                Console.WriteLine("Text : {0} ", textFragment.Text);
                Console.WriteLine("Position : {0} ", textFragment.Position);
                Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
                Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
                Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
                Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
                Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
                Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
                Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
                Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
            }
```