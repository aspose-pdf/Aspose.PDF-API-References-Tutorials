---
title: Remove All Text From PDF
linktitle: Remove All Text From PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 290
url: /net/programming-with-text/remove-all-text-from-pdf/
---
### Sample source code for Remove All Text From PDF using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
            // Initiate TextFragmentAbsorber
            TextFragmentAbsorber absorber = new TextFragmentAbsorber();
            // Remove all absorbed text
            absorber.RemoveAllText(pdfDocument);
            // Save the document
            pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```