---
title: Add HTMLUsing DOMAnd Overwrite
linktitle: Add HTMLUsing DOMAnd Overwrite
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /net/programming-with-text/add-htmlusing-domand-overwrite/
---
### Sample source code for Add HTMLUsing DOMAnd Overwrite using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate Document object
            Document doc = new Document();
            // Add a page to pages collection of PDF file
            Page page = doc.Pages.Add();
            // Instantiate HtmlFragment with HTML contnets
            HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
            //Font-family from 'Verdana' will be reset to 'Arial'
            title.TextState = new TextState("Arial");
            title.TextState.FontSize = 20;
            // Set bottom margin information
            title.Margin.Bottom = 10;
            // Set top margin information
            title.Margin.Top = 400;
            // Add HTML Fragment to paragraphs collection of page
            page.Paragraphs.Add(title);
            // Save PDF file
            dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
            // Save PDF file
            doc.Save(dataDir);
```