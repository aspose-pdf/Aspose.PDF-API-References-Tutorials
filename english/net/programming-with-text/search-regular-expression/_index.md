---
title: Search Regular Expression
linktitle: Search Regular Expression
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 440
url: /net/programming-with-text/search-regular-expression/
---
### Sample source code for Search Regular Expression using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
            // Create TextAbsorber object to find all the phrases matching the regular expression
            TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Like 1999-2000
            // Set text search option to specify regular expression usage
            TextSearchOptions textSearchOptions = new TextSearchOptions(true);
            textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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