---
title: Extract Text From Stamp Annotation
linktitle: Extract Text From Stamp Annotation
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
### Sample source code for Extract Text From Stamp Annotation using Aspose.PDF for .NET 
```csharp
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "test.pdf");
            StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
            TextAbsorber ta = new TextAbsorber();
            XForm ap = annot.Appearance["N"];
            ta.Visit(ap);
            Console.WriteLine(ta.Text);
```