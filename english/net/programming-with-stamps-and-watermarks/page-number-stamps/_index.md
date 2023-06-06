---
title: Page Number Stamps
linktitle: Page Number Stamps
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 160
url: /net/programming-with-stamps-and-watermarks/page-number-stamps/
---
### Sample source code for Page Number Stamps using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");
            // Create page number stamp
            PageNumberStamp pageNumberStamp = new PageNumberStamp();
            // Whether the stamp is background
            pageNumberStamp.Background = false;
            pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
            pageNumberStamp.BottomMargin = 10;
            pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
            pageNumberStamp.StartingNumber = 1;
            // Set text properties
            pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
            pageNumberStamp.TextState.FontSize = 14.0F;
            pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
            pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
            pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
            // Add stamp to particular page
            pdfDocument.Pages[1].AddStamp(pageNumberStamp);
            dataDir = dataDir + "PageNumberStamp_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```