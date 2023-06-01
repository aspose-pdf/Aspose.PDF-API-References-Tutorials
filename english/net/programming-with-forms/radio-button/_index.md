---
title: Radio Button
linktitle: Radio Button
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 220
url: /pdf/net/programming-with-forms/radio-button/
---
### Sample source code for Radio Button using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
                // Instantiate Document object
                Document pdfDocument = new Document();
                // Add a page to PDF file
                pdfDocument.Pages.Add();
                // Instatiate RadioButtonField object with page number as argument
                RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
                // Add first radio button option and also specify its origin using Rectangle object
                radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
                // Add second radio button option
                radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
                // Add radio button to form object of Document object
                pdfDocument.Form.Add(radio);
                dataDir = dataDir + "RadioButton_out.pdf";
                // Save the PDF file
                pdfDocument.Save(dataDir);
                Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```