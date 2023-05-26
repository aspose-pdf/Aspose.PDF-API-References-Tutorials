---
title: Strike Out Words
linktitle: Strike Out Words
second_title: Aspose.PDF for .NET API Reference
description: This article provides a step-by-step guide to using Aspose.PDF for .NET's Strike Out Words feature, including step by step guide and explanations
type: docs
weight: 150
url: /net/annotations/strikeoutwords/
---
Aspose.PDF for .NET is a PDF document manipulation and processing library that provides various features to create, modify, and convert PDF files. One of the useful features that Aspose.PDF provides is the ability to strike out words or phrases in a PDF document using C# source code. In this article, we will provide a step-by-step guide on how to strike out words using Aspose.PDF for .NET.

## Loading the PDF document
The first step is to load the PDF document that you want to modify. In this tutorial, we will load a PDF document named "input.pdf" from the "YOUR DOCUMENT DIRECTORY" folder. 

```
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Searching for text fragments
To strike out specific words or phrases in the PDF document, you first need to search for them. Aspose.PDF provides a TextFragmentAbsorber class that can be used to search for a specific text fragment in the PDF document.

```
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

In the above code, we are searching for the text fragment "Estoque" in the PDF document. You can modify this to search for any other word or phrase that you want to strike out.

## Striking out the text fragments
After finding the text fragments, the next step is to strike them out. Aspose.PDF provides a StrikeOutAnnotation class that can be used to create a strike-out annotation for the text fragment. 

```
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

In the above code, we are creating a strike-out annotation for each text fragment that we found. We are setting the opacity, border, and color of the strike-out annotation as well.

## Saving the modified PDF document
After striking out the text fragments, the save the modified document.

```
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Example source code for Strike Out Words using Aspose.PDF for .NET


```csharp

            
            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Open document
            Document document = new Document(dataDir + "input.pdf");

            // Create TextFragment Absorber instance to search particular text fragment
            Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
            // Iterate through pages of PDF document
            for (int i = 1; i <= document.Pages.Count; i++)
            {
                // Get first page of PDF document
                Page page = document.Pages[1];
                page.Accept(textFragmentAbsorber);
            }

            // Create a collection of Absorbed text
            Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

            // Iterate on above collection
            for (int j = 1; j <= textFragmentCollection.Count; j++)
            {
                Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

                // Get rectangular dimensions of TextFragment object  	
                Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
                            (float)textFragment.Position.XIndent,
                            (float)textFragment.Position.YIndent,
                            (float)textFragment.Position.XIndent +
                            (float)textFragment.Rectangle.Width,
                            (float)textFragment.Position.YIndent +
                            (float)textFragment.Rectangle.Height);

                // Instantiate StrikeOut Annotation instance
                StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
                // Set opacity for annotation
                strikeOut.Opacity = .80f;
                // Set the border for annotation instance
                strikeOut.Border = new Border(strikeOut);
                // Set the color of annotation
                strikeOut.Color = Aspose.Pdf.Color.Red;
                // Add annotation to annotations collection of TextFragment
                textFragment.Page.Annotations.Add(strikeOut);
            }
            dataDir = dataDir + "StrikeOutWords_out.pdf";
            document.Save(dataDir);


        
```

