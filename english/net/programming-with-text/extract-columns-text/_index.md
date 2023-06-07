---
title: Extract Columns Text
linktitle: Extract Columns Text
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 150
url: /net/programming-with-text/extract-columns-text/
---
### Sample source code for Extract Columns Text using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
            TextFragmentAbsorber tfa = new TextFragmentAbsorber();
            pdfDocument.Pages.Accept(tfa);
            TextFragmentCollection tfc = tfa.TextFragments;
            foreach (TextFragment tf in tfc)
            {
                // Need to reduce font size at least for 70%
                tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
            }
            Stream st = new MemoryStream();
            pdfDocument.Save(st);
            pdfDocument = new Document(st);
            TextAbsorber textAbsorber = new TextAbsorber();
            pdfDocument.Pages.Accept(textAbsorber);
            String extractedText = textAbsorber.Text;
            textAbsorber.Visit(pdfDocument); 
            dataDir = dataDir + "ExtractColumnsText_out.txt";
            System.IO.File.WriteAllText(dataDir, extractedText);           
            Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```