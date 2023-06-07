---
title: Add HTMLUsing DOM
linktitle: Add HTMLUsing DOM
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/programming-with-text/add-htmlusing-dom/
---
### Sample source code for Add HTMLUsing DOM using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate Document object
            Document doc = new Document();
            // Add a page to pages collection of PDF file
            Page page = doc.Pages.Add();
            // Instantiate HtmlFragment with HTML contnets
            HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
            // Set bottom margin information
            titel.Margin.Bottom = 10;
            // Set top margin information
            titel.Margin.Top = 200;
            // Add HTML Fragment to paragraphs collection of page
            page.Paragraphs.Add(titel);
            dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
            // Save PDF file
            doc.Save(dataDir);
            Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```