---
title: Create Application Link
linktitle: Create Application Link
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /net/programming-with-links-and-actions/create-application-link/
---
### Sample source code for Create Application Link using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document document = new Document( dataDir + "CreateApplicationLink.pdf");
            // Create link
            Page page = document.Pages[1];
            LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
            link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
            link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
            page.Annotations.Add(link);
            dataDir = dataDir + "CreateApplicationLink_out.pdf";
            // Save updated document
            document.Save(dataDir);
            Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```