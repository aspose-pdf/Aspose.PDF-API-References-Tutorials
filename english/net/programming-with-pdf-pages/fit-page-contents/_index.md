---
title: Fit Page Contents
linktitle: Fit Page Contents
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /pdf/net/programming-with-pdf-pages/fit-page-contents/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            Document doc = new Document(dataDir + "input.pdf");
            foreach (Page page in doc.Pages)
            {
                Rectangle r = page.MediaBox;
                // New height the same
                double newHeight = r.Height;
                // New width is expanded proportionally to make orientation landscape
                // (we assume that previous orientation is portrait)
                double newWidth = r.Height * r.Height / r.Width;

            }          
            
            
        
```

