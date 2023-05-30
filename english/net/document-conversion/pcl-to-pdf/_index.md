---
title: PCL to PDF
linktitle: PCL to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /pdf/net/document-conversion/pcl-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";

                // Instantiate LoadOption object using PCL load option
                Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.PclLoadOptions();

                // Create Document object
                Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "hidetext.pcl", loadopt);

                // Save the resultant PDF document
                doc.Save(dataDir + "PCLToPDF_out.pdf");
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

