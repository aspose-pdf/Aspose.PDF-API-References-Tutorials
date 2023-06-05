---
title: Update Links
linktitle: Update Links
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /net/programming-with-links-and-actions/update-links/
---
### Sample source code for Update Links using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load the PDF file
                Document doc = new Document(dataDir + "UpdateLinks.pdf");
                // Get the first link annotation from first page of document
                LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
                // Modification link: change link destination
                GoToAction goToAction = (GoToAction)linkAnnot.Action;
                // Specify the destination for link object
                // The first parameter is document object, second is destination page number.
                // The 5ht argument is zoom factor when displaying the respective page. When using 2, the page will be displayed in 200% zoom
                goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
                dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
                // Save the document with updated link
                doc.Save(dataDir);
                Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```