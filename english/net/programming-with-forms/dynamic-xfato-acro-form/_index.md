---
title: Dynamic XFATo Acro Form
linktitle: Dynamic XFATo Acro Form
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /pdf/net/programming-with-forms/dynamic-xfato-acro-form/
---
### Sample source code for Dynamic XFATo Acro Form using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load dynamic XFA form
            Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
            // Set the form fields type as standard AcroForm
            document.Form.Type = FormType.Standard;
            dataDir = dataDir + "Standard_AcroForm_out.pdf";
            // Save the resultant PDF
            document.Save(dataDir);
            Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```