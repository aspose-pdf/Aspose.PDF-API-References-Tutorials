---
title: Create Document Link
linktitle: Create Document Link
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /net/programming-with-links-and-actions/create-document-link/
---
### Sample source code for Create Document Link using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
            // Create link
            Page page = document.Pages[1];
            LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
            link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
            link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
            page.Annotations.Add(link);
            dataDir = dataDir + "CreateDocumentLink_out.pdf";
            // Save updated document
            document.Save(dataDir);
            Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```