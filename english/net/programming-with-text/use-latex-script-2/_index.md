---
title: Use Latex Script 2
linktitle: Use Latex Script 2
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 560
url: /net/programming-with-text/use-latex-script-2/
---
### Sample source code for Use Latex Script 2 using Aspose.PDF for .NET 
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
            string latexText2 = @"\documentclass{article}
                                \begin{document}
                                Latex and the document class will normally take care of page layout issues for you. For submission to an academic publication, this entire topic will be out
                                \end{document}";
            Cell cell = row.Cells.Add();
            cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
            HtmlFragment text2 = new HtmlFragment(latexText2);
            cell.Paragraphs.Add(text2);
            // Add table inside page
            page.Paragraphs.Add(table);
            // Save the document
            doc.Save(dataDir + "LatextScriptInPdf2_out.pdf");
```