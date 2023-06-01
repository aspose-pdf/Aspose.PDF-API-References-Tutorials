---
title: Arabic Text Filling
linktitle: Arabic Text Filling
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /pdf/net/programming-with-forms/arabic-text-filling/
---
### Sample source code for Arabic Text Filling using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load PDF form contents
            FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
            // Instantiate Document instance with stream holding form file
            Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
            // Get referecne of particuarl TextBoxField
            TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
            // Fill form field with arabic text
            txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
            dataDir = dataDir + "ArabicTextFilling_out.pdf";
            // Save updated document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```