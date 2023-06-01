---
title: Determine Required Field
linktitle: Determine Required Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /pdf/net/programming-with-forms/determine-required-field/
---
### Sample source code for Determine Required Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load source PDF file
            Document pdf = new Document(dataDir + "DetermineRequiredField.pdf");
            // Instantiate Form object
            Aspose.Pdf.Facades.Form pdfForm = new Aspose.Pdf.Facades.Form(pdf);
            // Iterate through each field inside PDF form
            foreach (Field field in pdf.Form.Fields)
            {
                // Determine if the field is marked as required or not
                bool isRequired = pdfForm.IsRequiredField(field.FullName);
                if (isRequired)
                {
                    // Print either the field is marked as required or not
                    Console.WriteLine("The field named " + field.FullName + " is required");
                }
            }
```