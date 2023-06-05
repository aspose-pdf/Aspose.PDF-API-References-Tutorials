---
title: Create Local Hyperlink
linktitle: Create Local Hyperlink
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/programming-with-links-and-actions/create-local-hyperlink/
---
### Sample source code for Create Local Hyperlink using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create Document instance
            Document doc = new Document();
            // Add page to pages collection of PDF file
            Page page = doc.Pages.Add();
            // Create Text Fragment instance
            Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
            // Create local hyperlink instance
            Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
            // Set target page for link instance
            link.TargetPageNumber = 7;
            // Set TextFragment hyperlink
            text.Hyperlink = link;
            // Add text to paragraphs collection of Page
            page.Paragraphs.Add(text);
            // Create new TextFragment instance
            text = new TextFragment("link page number test to page 1");
            // TextFragment should be added over new page
            text.IsInNewPage = true;
            // Create another local hyperlink instance
            link = new LocalHyperlink();
            // Set Target page for second hyperlink
            link.TargetPageNumber = 1;
            // Set link for second TextFragment
            text.Hyperlink = link;
            // Add text to paragraphs collection of page object
            page.Paragraphs.Add(text);    
            dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
            // Save updated document
            doc.Save(dataDir);
            Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```