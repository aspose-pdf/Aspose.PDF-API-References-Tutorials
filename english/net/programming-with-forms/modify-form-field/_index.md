---
title: Modify Form Field
linktitle: Modify Form Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 190
url: /pdf/net/programming-with-forms/modify-form-field/
---
### Sample source code for Modify Form Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
            // Get a field
            TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
            // Modify field value
            textBoxField.Value = "New Value";
            textBoxField.ReadOnly = true;
            dataDir = dataDir + "ModifyFormField_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```