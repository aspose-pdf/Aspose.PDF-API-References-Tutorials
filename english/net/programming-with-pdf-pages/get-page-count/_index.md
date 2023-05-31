---
title: Get Page Count
linktitle: Get Page Count
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /pdf/net/programming-with-pdf-pages/get-page-count/
---



```csharp

            
            // Instantiate Document instance
            Document doc = new Document();
            // Add page to pages collection of PDF file
            Page page = doc.Pages.Add();
            // Create loop instance
            for (int i = 0; i < 300; i++)
                // Add TextFragment to paragraphs collection of page object
                page.Paragraphs.Add(new TextFragment("Pages count test"));
            // Process the paragraphs in PDF file to get accurate page count
            doc.ProcessParagraphs();
            // Print number of pages in document
            Console.WriteLine("Number of pages in document = " + doc.Pages.Count);
            
        
```

