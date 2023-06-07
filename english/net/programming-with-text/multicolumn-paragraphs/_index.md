---
title: Multicolumn Paragraphs
linktitle: Multicolumn Paragraphs
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 250
url: /net/programming-with-text/multicolumn-paragraphs/
---
### Sample source code for Multicolumn Paragraphs using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
            ParagraphAbsorber absorber = new ParagraphAbsorber();
            absorber.Visit(doc);
            PageMarkup markup = absorber.PageMarkups[0];
            Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
            MarkupSection section = markup.Sections[2];
            MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
            Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
            Console.WriteLine(paragraph.Text);
            section = markup.Sections[1];
            paragraph = section.Paragraphs[0];
            Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
            Console.WriteLine(paragraph.Text);
            markup.IsMulticolumnParagraphsAllowed = true;
            Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
            section = markup.Sections[2];
            paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
            Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
            Console.WriteLine(paragraph.Text);
            section = markup.Sections[1];
            paragraph = section.Paragraphs[0];
            Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
            Console.WriteLine(paragraph.Text);
```