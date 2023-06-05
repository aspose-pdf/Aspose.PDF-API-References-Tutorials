---
title: Set Target Link
linktitle: Set Target Link
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /net/programming-with-links-and-actions/set-target-link/
---
### Sample source code for Set Target Link using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load the PDF file
                Document document = new Document(dataDir + "UpdateLinks.pdf");
                LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
                GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
                // Next line update destination, do not update file
                goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
                // Next line update file
                goToR.File = new FileSpecification(dataDir +  "input.pdf");
                dataDir = dataDir + "SetTargetLink_out.pdf";
                // Save the document with updated link
                document.Save(dataDir);
                Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```