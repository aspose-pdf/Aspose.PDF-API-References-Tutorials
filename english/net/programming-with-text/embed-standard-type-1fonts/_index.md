---
title: Embed Standard Type 1Fonts
linktitle: Embed Standard Type 1Fonts
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 140
url: /net/programming-with-text/embed-standard-type-1fonts/
---
### Sample source code for Embed Standard Type 1Fonts using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Load an existing PDF Document
            Document pdfDocument = new Document(dataDir + "input.pdf");
            // Set EmbedStandardFonts property of document
            pdfDocument.EmbedStandardFonts = true;
            foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
            {
                if (page.Resources.Fonts != null)
                {
                    foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
                    {
                        // Check if font is already embedded
                        if (!pageFont.IsEmbedded)
                        {
                            pageFont.IsEmbedded = true;
                        }
                    }
                }
            }
            pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```