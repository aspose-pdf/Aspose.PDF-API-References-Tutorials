---
title: XPS to PDF
linktitle: XPS to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 350
url: /pdf/net/document-conversion/xps-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";

                // Instantiate LoadOption object using XPS load option
                Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

                // Create document object 
                Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

                // Save the resultant PDF document
                document.Save(dataDir + "XPSToPDF_out.pdf");
                
            }
            catch(Exception ex)
               
            {
                Console.WriteLine(ex.Message);
            }
        
```

