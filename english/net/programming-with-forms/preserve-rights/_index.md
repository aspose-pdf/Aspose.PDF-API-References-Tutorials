---
title: Preserve Rights
linktitle: Preserve Rights
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 210
url: /pdf/net/programming-with-forms/preserve-rights/
---
### Sample source code for Preserve Rights using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Read the source PDF form with FileAccess of Read and Write.
            // We need ReadWrite permission because after modification,
            // We need to save the updated contents in same document/file.
            FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
            // Instantiate Document instance
            Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
            // Get values from all fields
            foreach (Field formField in pdfDocument.Form)
            {
                // If the fullname of field contains A1, perform the operation
                if (formField.FullName.Contains("A1"))
                {
                    // Cast form field as TextBox
                    TextBoxField textBoxField = formField as TextBoxField;
                    // Modify field value
                    textBoxField.Value = "Testing";
                }
            }
            // Save the updated document in save FileStream
            pdfDocument.Save();
            // Close the File Stream object
            fs.Close();
```