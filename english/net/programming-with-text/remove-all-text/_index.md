---
title: Remove All Text
linktitle: Remove All Text
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 280
url: /net/programming-with-text/remove-all-text/
---
### Sample source code for Remove All Text using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
            // Loop through all pages of PDF Document
            for (int i = 1; i <= pdfDocument.Pages.Count; i++)
            {
                Page page = pdfDocument.Pages[i];
                OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
                // Select all text on the page
                page.Contents.Accept(operatorSelector);
                // Delete all text
                page.Contents.Delete(operatorSelector.Selected);
            }
            // Save the document
            pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```