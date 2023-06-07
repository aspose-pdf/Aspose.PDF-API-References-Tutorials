---
title: Remove Unused Fonts
linktitle: Remove Unused Fonts
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 300
url: /net/programming-with-text/remove-unused-fonts/
---
### Sample source code for Remove Unused Fonts using Aspose.PDF for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load source PDF file
                Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
                TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
                doc.Pages.Accept(absorber);
                // Iterate through all the TextFragments
                foreach (TextFragment textFragment in absorber.TextFragments)
                {
                    textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
                }
                dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
                // Save updated document
                doc.Save(dataDir);
                Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
            }
```