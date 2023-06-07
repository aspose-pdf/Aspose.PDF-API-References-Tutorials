---
title: Text And Image As Paragraph
linktitle: Text And Image As Paragraph
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 530
url: /net/programming-with-text/text-and-image-as-paragraph/
---
### Sample source code for Text And Image As Paragraph using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate Document instance
            Document doc = new Document();
            // Add page to pages collection of Document instance
            Page page = doc.Pages.Add();
            // Create TextFragmnet
            TextFragment text = new TextFragment("Hello World.. ");
            // Add text fragment to paragraphs collection of Page object
            page.Paragraphs.Add(text);
            // Create an image instance
            Aspose.Pdf.Image image = new Aspose.Pdf.Image();
            // Set image as inline paragraph so that it appears right after 
            // The previous paragraph object (TextFragment)
            image.IsInLineParagraph = true;
            // Specify image file path 
            image.File = dataDir + "aspose-logo.jpg";
            // Set image Height (optional)
            image.FixHeight = 30;
            // Set Image Width (optional)
            image.FixWidth = 100;
            // Add image to paragraphs collection of page object
            page.Paragraphs.Add(image);
            // Re-initialize TextFragment object with different contents
            text = new TextFragment(" Hello Again..");
            // Set TextFragment as inline paragraph
            text.IsInLineParagraph = true;
            // Add newly created TextFragment to paragraphs collection of page
            page.Paragraphs.Add(text);
            dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
            doc.Save(dataDir);
            Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```