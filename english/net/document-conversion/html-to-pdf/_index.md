---
title: HTML to PDF
linktitle: HTML to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /pdf/net/document-conversion/html-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";

                HtmlLoadOptions options = new HtmlLoadOptions();
                options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

                Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
                pdfDocument.Save("HTMLToPDF_out.pdf");
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

