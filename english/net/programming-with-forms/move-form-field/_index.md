---
title: Move Form Field
linktitle: Move Form Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 200
url: /pdf/net/programming-with-forms/move-form-field/
---
### Sample source code for Move Form Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
            // Get a field
            TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
            // Modify field location
            textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
            dataDir = dataDir + "MoveFormField_out.pdf";
            // Save modified document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```