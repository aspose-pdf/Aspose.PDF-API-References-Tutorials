---
title: Get Hyperlink Text
linktitle: Get Hyperlink Text
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /net/programming-with-links-and-actions/get-hyperlink-text/
---
### Sample source code for Get Hyperlink Text using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load the PDF file
                Document document = new Document(dataDir + "input.pdf");
                // Iterate through each page of PDF
                foreach (Page page in document.Pages)
                {
                    // Show link annotation
                    ShowLinkAnnotations(page);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```