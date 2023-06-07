---
title: Replace Fonts
linktitle: Replace Fonts
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 340
url: /net/programming-with-text/replace-fonts/
---
### Sample source code for Replace Fonts using Aspose.PDF for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load source PDF file
                Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
                // Search text fragments and set edit option as remove unused fonts
                TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
                // Accept the absorber for all the pages
                pdfDocument.Pages.Accept(absorber);
                // Traverse through all the TextFragments
                foreach (TextFragment textFragment in absorber.TextFragments)
                {
                    // If the font name is ArialMT, replace font name with Arial
                    if (textFragment.TextState.Font.FontName == "Arial,Bold")
                    {
                        textFragment.TextState.Font = FontRepository.FindFont("Arial");
                    }
                }
                dataDir = dataDir + "ReplaceFonts_out.pdf";
                // Save updated document
                pdfDocument.Save(dataDir);
                Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
            }
```