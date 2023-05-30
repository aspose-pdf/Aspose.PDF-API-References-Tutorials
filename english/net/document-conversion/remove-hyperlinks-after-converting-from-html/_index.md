---
title: Remove Hyperlinks After Converting From Html
linktitle: Remove Hyperlinks After Converting From Html
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 250
url: /pdf/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
            doc.Save(new MemoryStream());
            foreach (Annotation a in doc.Pages[1].Annotations)
            {
                if (a.AnnotationType == AnnotationType.Link)
                {
                    LinkAnnotation la = (LinkAnnotation)a;
                    if (la.Action is GoToURIAction)
                    {
                        GoToURIAction gta = (GoToURIAction)la.Action;
                        gta.URI = "";
                        TextFragmentAbsorber tfa = new TextFragmentAbsorber();
                        tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
                        doc.Pages[a.PageIndex].Accept(tfa);
                        foreach (TextFragment tf in tfa.TextFragments)
                        {
                            tf.TextState.Underline = false;
                            tf.TextState.ForegroundColor = Color.Black;
                        }
                    }
                    doc.Pages[a.PageIndex].Annotations.Delete(a);
                }
            }
            doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
            
        
```

