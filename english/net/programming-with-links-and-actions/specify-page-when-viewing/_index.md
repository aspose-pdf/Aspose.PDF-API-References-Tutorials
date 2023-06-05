---
title: Specify Page When Viewing
linktitle: Specify Page When Viewing
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /net/programming-with-links-and-actions/specify-page-when-viewing/
---
### Sample source code for Specify Page When Viewing using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Load the PDF file
            Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
            // Get the instance of second page of document
            Page page2 = doc.Pages[2];
            // Create the variable to set the zoom factor of target page
            double zoom = 1;
            // Create GoToAction instance
            GoToAction action = new GoToAction(doc.Pages[2]);
            // Go to 2 page
            action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
            // Set the document open action
            doc.OpenAction = action;
            // Save updated document
            doc.Save(dataDir + "goto2page_out.pdf");
```