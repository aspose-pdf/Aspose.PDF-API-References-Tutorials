---
title: Tagged PDFContent
linktitle: Tagged PDFContent
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 200
url: /net/programming-with-tagged-pdf/tagged-pdfcontent/
---
### Sample source code for Tagged PDFContent using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create Pdf Document
            Document document = new Document();
            // Get Content for work with TaggedPdf
            ITaggedContent taggedContent = document.TaggedContent;
            //
            // Work with Tagged Pdf content
            //
            // Set Title and Language for Documnet
            taggedContent.SetTitle("Simple Tagged Pdf Document");
            taggedContent.SetLanguage("en-US");
            // Save Tagged Pdf Document
            document.Save(dataDir + "TaggedPDFContent.pdf");
```