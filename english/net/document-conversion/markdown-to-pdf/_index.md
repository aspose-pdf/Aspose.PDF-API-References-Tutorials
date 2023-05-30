---
title: Markdown to PDF
linktitle: Markdown to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /pdf/net/document-conversion/markdown-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open Markdown document
            Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
            // Save document in PDF format
            doc.Save(dataDir + "MarkdownToPDF.pdf");
            
        
```

