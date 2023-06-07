---
title: Extract Paragraphs
linktitle: Extract Paragraphs
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 160
url: /net/programming-with-text/extract-paragraphs/
---
### Sample source code for Extract Paragraphs using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open an existing PDF file
            Document doc = new Document(dataDir + "input.pdf");
            // Instantiate ParagraphAbsorber
            ParagraphAbsorber absorber = new ParagraphAbsorber();
            absorber.Visit(doc);
            foreach (PageMarkup markup in absorber.PageMarkups)
            {
                int i = 1;
                foreach (MarkupSection section in markup.Sections)
                {
                    int j = 1;
                    foreach (MarkupParagraph paragraph in section.Paragraphs)
                    {
                        StringBuilder paragraphText = new StringBuilder();
                        foreach (List<TextFragment> line in paragraph.Lines)
                        {
                            foreach (TextFragment fragment in line)
                            {
                                paragraphText.Append(fragment.Text);
                            }
                            paragraphText.Append("\r\n");
                        }
                        paragraphText.Append("\r\n");
                        Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
                        Console.WriteLine(paragraphText.ToString());
                        j++;
                    }
                    i++;
                }
            }
```