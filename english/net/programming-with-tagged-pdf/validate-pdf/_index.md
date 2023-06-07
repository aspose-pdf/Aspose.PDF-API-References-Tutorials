---
title: Validate PDF
linktitle: Validate PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 240
url: /net/programming-with-tagged-pdf/validate-pdf/
---
### Sample source code for Validate PDF using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inputFileName = dataDir + "StructureElements.pdf";
            string outputLogName = dataDir + "ua-20.xml";
            using (var document = new Aspose.Pdf.Document(inputFileName))
            {
                bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
            }
```