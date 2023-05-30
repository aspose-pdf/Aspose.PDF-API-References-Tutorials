---
title: PDF to XML
linktitle: PDF to XML
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 210
url: /pdf/net/document-conversion/pdf-to-xml/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";            
            // Load source PDF file
            Document doc = new Document(dataDir + "input.pdf");
            // Save output in XML format
            doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
            
        
```

