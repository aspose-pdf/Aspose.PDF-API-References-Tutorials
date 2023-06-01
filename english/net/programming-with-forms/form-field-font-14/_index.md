---
title: Form Field Font 14
linktitle: Form Field Font 14
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /pdf/net/programming-with-forms/form-field-font-14/
---
### Sample source code for Form Field Font 14 using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
            // Get particular form field from document
            Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
            // Create font object
            Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
            // Set the font information for form field
            // Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
            dataDir = dataDir + "FormFieldFont14_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```