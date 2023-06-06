---
title: Imageand Page Numberin Header Footersection Inline
linktitle: Imageand Page Numberin Header Footersection Inline
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /net/programming-with-stamps-and-watermarks/imageand-page-numberin-header-footersection-inline/
---
### Sample source code for Imageand Page Numberin Header Footersection Inline using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Instantiate a Document object by calling its empty constructor
            Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
            // Create a page in the Pdf object
            Aspose.Pdf.Page page = pdf1.Pages.Add();
            // Create Header Section of the document
            Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
            // Set the header for the PDF file
            page.Header = header;
            // Create a Text object
            Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
            // Specify the color
            txt1.TextState.ForegroundColor = Color.Blue;
            txt1.IsInLineParagraph = true;
            // Create an image object in the section
            Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
            // Set the path of image file
            image1.File = dataDir + "aspose-logo.jpg";
            // Set the image width Information
            image1.FixWidth = 50;
            image1.FixHeight = 20;
            // Indicate seg1's InlineParagraph is a image.
            image1.IsInLineParagraph = true;
            Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
            txt2.IsInLineParagraph = true;
            txt2.TextState.ForegroundColor = Color.Maroon;
            header.Paragraphs.Add(txt1);
            header.Paragraphs.Add(image1);
            header.Paragraphs.Add(txt2);
            // Save the Pdf
            pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```