---
title: Counting Artifacts
linktitle: Counting Artifacts
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /net/programming-with-stamps-and-watermarks/counting-artifacts/
---
### Sample source code for Counting Artifacts using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document( dataDir +  "watermark.pdf");
            int count = 0;
            foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
            {
                // If artifact type is watermark, increate the counter
                if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
            }
            Console.WriteLine("Page contains " + count + " watermarks");
```