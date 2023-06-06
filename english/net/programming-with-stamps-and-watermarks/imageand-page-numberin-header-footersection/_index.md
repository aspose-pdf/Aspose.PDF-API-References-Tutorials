---
title: Imageand Page Numberin Header Footersection
linktitle: Imageand Page Numberin Header Footersection
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /net/programming-with-stamps-and-watermarks/imageand-page-numberin-header-footersection/
---
### Sample source code for Imageand Page Numberin Header Footersection using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
            // Create a page in the document object
            Aspose.Pdf.Page page = doc.Pages.Add();
            // Create Header Section of the document
            Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
            // Set the header for the PDF file
            page.Header = header;
            // Create an image object in the page
            Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
            // Set the path of image file
            image1.File = dataDir + "aspose-logo.jpg";
            // Add image to Header page of the Pdf file
            header.Paragraphs.Add(image1);
            // Create a Footer Section of the document
            Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
            // Set the footer of the PDF file
            page.Footer = footer;
            // Create a Text object
            Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
            // Add text to Header section of the Pdf file
            footer.Paragraphs.Add(txt);
            // Save the Pdf file
            doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```