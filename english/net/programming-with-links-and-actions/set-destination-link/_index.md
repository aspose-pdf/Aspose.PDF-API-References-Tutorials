---
title: Set Destination Link
linktitle: Set Destination Link
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /net/programming-with-links-and-actions/set-destination-link/
---
### Sample source code for Set Destination Link using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load the PDF file
                Document doc = new Document(dataDir + "UpdateLinks.pdf");
                // Get the first link annotation from first page of document
                LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
                // Modification link: change link action and set target as web address
                linkAnnot.Action = new GoToURIAction("www.aspose.com");           
                dataDir = dataDir + "SetDestinationLink_out.pdf";
                // Save the document with updated link
                doc.Save(dataDir);
                Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```