---
title: Get Watermark
linktitle: Get Watermark
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /net/programming-with-stamps-and-watermarks/get-watermark/
---
### Sample source code for Get Watermark using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document( dataDir +  "watermark.pdf");
            // Iterate through and get tub-type, text and location of artifact
            foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
            {
                Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
            }
```