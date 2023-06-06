---
title: Define Alignment
linktitle: Define Alignment
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /net/programming-with-stamps-and-watermarks/define-alignment/
---
### Sample source code for Define Alignment using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate Document object with input file
            Document doc = new Document(dataDir+ "DefineAlignment.pdf");
            // Instantiate FormattedText object with sample string
            FormattedText text = new FormattedText("This");
            // Add new text line to FormattedText
            text.AddNewLineText("is sample");
            text.AddNewLineText("Center Aligned");
            text.AddNewLineText("TextStamp");
            text.AddNewLineText("Object");
            // Create TextStamp object using FormattedText
            TextStamp stamp = new TextStamp(text);
            // Specify the Horizontal Alignment of text stamp as Center aligned
            stamp.HorizontalAlignment = HorizontalAlignment.Center;
            // Specify the Vertical Alignment of text stamp as Center aligned
            stamp.VerticalAlignment = VerticalAlignment.Center;
            // Specify the Text Horizontal Alignment of TextStamp as Center aligned
            stamp.TextAlignment = HorizontalAlignment.Center;
            // Set top margin for stamp object
            stamp.TopMargin = 20;
            // Add the stamp object over first page of document
            doc.Pages[1].AddStamp(stamp);
            dataDir = dataDir + "StampedPDF_out.pdf";
            // Save the udpated document
            doc.Save(dataDir);
            Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);
```