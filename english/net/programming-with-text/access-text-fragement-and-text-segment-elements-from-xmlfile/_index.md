---
title: Access Text Fragement And Text Segment Elements From XMLFile
linktitle: Access Text Fragement And Text Segment Elements From XMLFile
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /net/programming-with-text/access-text-fragement-and-text-segment-elements-from-xmlfile/
---
### Sample source code for Access Text Fragement And Text Segment Elements From XMLFile using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inXml = "40014.xml";
            string outFile = "40014_out.pdf";
            Document doc = new Document();
            doc.BindXml(dataDir + inXml);
            Page page = (Page)doc.GetObjectById("mainSection");
            TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
            segment = (TextSegment)doc.GetObjectById("strongHtml");
            doc.Save(dataDir + outFile);
```