---
title: Use Latex Script
linktitle: Use Latex Script
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 550
url: /net/programming-with-text/use-latex-script/
---
### Sample source code for Use Latex Script using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create a new Document Object
            Document doc = new Document();
            // Add Page in Pages Collection
            Page page = doc.Pages.Add();
            // Create a Table
            Table table = new Table();
            // Add a row into Table
            Row row = table.Rows.Add();
            // Add Cell with Latex Script to add methematical expressions/formulae
            string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
            Cell cell = row.Cells.Add();
            cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
            // Second LatexFragment constructor bool parameter provides LaTeX paragraph indents elimination.
            LatexFragment ltext1 = new LatexFragment(latexText1, true);
            cell.Paragraphs.Add(ltext1);
            // Add table inside page
            page.Paragraphs.Add(table);
            // Save the document
            doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```