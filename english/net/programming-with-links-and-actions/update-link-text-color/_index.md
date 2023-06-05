---
title: Update Link Text Color
linktitle: Update Link Text Color
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 130
url: /net/programming-with-links-and-actions/update-link-text-color/
---
### Sample source code for Update Link Text Color using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Load the PDF file
                Document doc = new Document(dataDir + "UpdateLinks.pdf");
                foreach (Annotation annotation in doc.Pages[1].Annotations)
                {
                    if (annotation is LinkAnnotation)
                    {
                        // Search the text under the annotation
                        TextFragmentAbsorber ta = new TextFragmentAbsorber();
                        Rectangle rect = annotation.Rect;
                        rect.LLX -= 10;
                        rect.LLY -= 10;
                        rect.URX += 10;
                        rect.URY += 10;
                        ta.TextSearchOptions = new TextSearchOptions(rect);
                        ta.Visit(doc.Pages[1]);
                        // Change color of the text.
                        foreach (TextFragment tf in ta.TextFragments)
                        {
                            tf.TextState.ForegroundColor = Color.Red;
                        }
                    }
                }
                dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
                // Save the document with updated link
                doc.Save(dataDir);
                Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```