---
title: Replace Text All
linktitle: Replace Text All
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 350
url: /net/programming-with-text/replace-text-all/
---
### Sample source code for Replace Text All using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
            // Create TextAbsorber object to find all instances of the input search phrase
            TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
            // Accept the absorber for all the pages
            pdfDocument.Pages.Accept(textFragmentAbsorber);
            // Get the extracted text fragments
            TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
            // Loop through the fragments
            foreach (TextFragment textFragment in textFragmentCollection)
            {
                // Update text and other properties
                textFragment.Text = "TEXT";
                textFragment.TextState.Font = FontRepository.FindFont("Verdana");
                textFragment.TextState.FontSize = 22;
                textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
                textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
            }
            dataDir = dataDir + "ReplaceTextAll_out.pdf";
            // Save resulting PDF document.
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```