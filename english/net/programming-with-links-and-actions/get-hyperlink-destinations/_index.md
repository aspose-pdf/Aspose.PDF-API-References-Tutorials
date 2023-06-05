---
title: Get Hyperlink Destinations
linktitle: Get Hyperlink Destinations
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /net/programming-with-links-and-actions/get-hyperlink-destinations/
---
### Sample source code for Get Hyperlink Destinations using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load the PDF file
                Document document = new Document(dataDir + "input.pdf");
                // Traverse through all the page of PDF
                foreach (Aspose.Pdf.Page page in document.Pages)
                {
                    // Get the link annotations from particular page
                    AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
                    page.Accept(selector);
                    // Create list holding all the links
                    IList<Annotation> list = selector.Selected;
                    // Iterate through invidiaul item inside list
                    foreach (LinkAnnotation a in list)
                    {
                        // Print the destination URL
                        Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```