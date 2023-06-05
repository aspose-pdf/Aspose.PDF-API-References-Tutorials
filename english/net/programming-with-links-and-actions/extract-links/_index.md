---
title: Extract Links
linktitle: Extract Links
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /net/programming-with-links-and-actions/extract-links/
---
### Sample source code for Extract Links using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document document = new Document(dataDir+ "ExtractLinks.pdf");
            // Extract actions
            Page page = document.Pages[1];
            AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
            page.Accept(selector);
            IList<Annotation> list = selector.Selected;
            Annotation annotation = (Annotation)list[0];
            dataDir = dataDir + "ExtractLinks_out.pdf";
            // Save updated document
            document.Save(dataDir);
            Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```