---
title: XML to PDF
linktitle: XML to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 330
url: /pdf/net/document-conversion/xml-to-pdf/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instantiate Document object
            Document doc = new Document();
            // Bind source XML file
            doc.BindXml( dataDir + "sample.xml");
            // Get reference of page object from XML
            Page page = (Page)doc.GetObjectById("mainSection");
            // Get reference of first TextSegment with ID boldHtml
            TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
            // Get reference of second TextSegment with ID strongHtml
            segment = (TextSegment)doc.GetObjectById("strongHtml");
            // Save resultant PDF file
            doc.Save(dataDir + "XMLToPDF_out.pdf");
            
        
```

