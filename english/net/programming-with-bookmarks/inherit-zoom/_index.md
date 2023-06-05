---
title: Inherit Zoom
linktitle: Inherit Zoom
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /net/programming-with-bookmarks/inherit-zoom/
---
### Sample source code for Inherit Zoom using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document doc = new Document(dataDir + "input.pdf");
            // Get outlines/bookmarks collection of PDF file
            OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
            // Set zoom level as 0
            XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
            // Add XYZExplicitDestination as action to outlines collection of PDF
            item.Action = new GoToAction(dest);
            // Add item to outlines collection of PDF file
            doc.Outlines.Add(item);
            dataDir = dataDir + "InheritZoom_out.pdf";
            // Save output
            doc.Save(dataDir);
            Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```