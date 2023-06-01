---
title: Select Radio Button
linktitle: Select Radio Button
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 250
url: /pdf/net/programming-with-forms/select-radio-button/
---
### Sample source code for Select Radio Button using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
                // Open document
                Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
                // Get a field
                RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
                // Specify the index of radio button from group
                radioField.Selected = 2;
                dataDir = dataDir + "SelectRadioButton_out.pdf";
                // Save the PDF file
                pdfDocument.Save(dataDir);
                Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```