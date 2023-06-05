---
title: Remove Open Action
linktitle: Remove Open Action
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /net/programming-with-links-and-actions/remove-open-action/
---
### Sample source code for Remove Open Action using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document document = new Document(dataDir + "RemoveOpenAction.pdf");
            // Remove document open action
            document.OpenAction = null;
            dataDir = dataDir + "RemoveOpenAction_out.pdf";
            // Save updated document
            document.Save(dataDir);
            Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```