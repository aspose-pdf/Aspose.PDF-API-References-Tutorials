---
title: XML to PDFSet Image Path
linktitle: XML to PDFSet Image Path
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 340
url: /pdf/net/document-conversion/xml-to-pdfset-image-path/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                string inXml = dataDir + "input.xml";
                string inFile = dataDir + "aspose-logo.jpg";
                string outFile = dataDir + "output_out.pdf";
                Document doc = new Document();
                doc.BindXml(inXml);
                Image image = (Image)doc.GetObjectById("testImg");
                image.File = inFile;
                doc.Save(outFile);
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

