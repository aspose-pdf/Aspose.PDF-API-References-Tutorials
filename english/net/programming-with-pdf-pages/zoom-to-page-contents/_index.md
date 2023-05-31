---
title: Zoom To Page Contents
linktitle: Zoom To Page Contents
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 160
url: /pdf/net/programming-with-pdf-pages/zoom-to-page-contents/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Load source PDF file
            Document doc = new Document(dataDir + "input.pdf");
            // Get rectangular region of first page of PDF
            Aspose.Pdf.Rectangle rect = doc.Pages[1].Rect;
            // Instantiate PdfPageEditor instance
            PdfPageEditor ppe = new PdfPageEditor();
            // Bind source PDF
            ppe.BindPdf(dataDir + "input.pdf");
            // Set zoom coefficient
            ppe.Zoom = (float)(rect.Width / rect.Height);
            // Update page size
            ppe.PageSize = new Aspose.Pdf.PageSize((float)rect.Height, (float)rect.Width);

            dataDir = dataDir + "ZoomToPageContents_out.pdf";
            // Save output file
            doc.Save(dataDir);
            
            System.Console.WriteLine("\nZoom to page contents applied successfully.\nFile saved at " + dataDir);
        
```

