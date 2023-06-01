---
title: Delete Form Field
linktitle: Delete Form Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /pdf/net/programming-with-forms/delete-form-field/
---
### Sample source code for Delete Form Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
            // Delete a particular field by name
            pdfDocument.Form.Delete("textbox1");
            dataDir = dataDir + "DeleteFormField_out.pdf";
            // Save modified document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```