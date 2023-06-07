---
title: Search Text With Dot Net Regex
linktitle: Search Text With Dot Net Regex
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 480
url: /net/programming-with-text/search-text-with-dot-net-regex/
---
### Sample source code for Search Text With Dot Net Regex using Aspose.PDF for .NET 
```csharp
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create Regex object to find all words
            System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
            // Open document
            Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
            // Get a particular page
            Page page = document.Pages[1];
            // Create TextAbsorber object to find all instances of the input regex
            TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
            textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
            // Accept the absorber for the page
            page.Accept(textFragmentAbsorber);
            // Get the extracted text fragments
            TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
            // Loop through the fragments
            foreach (TextFragment textFragment in textFragmentCollection)
            {
                Console.WriteLine(textFragment.Text);
            }
```