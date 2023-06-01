---
title: Text Box
linktitle: Text Box
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 290
url: /pdf/net/programming-with-forms/text-box/
---
### Sample source code for Text Box using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "TextField.pdf");
            // Create a field
            TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
            textBoxField.PartialName = "textbox1";
            textBoxField.Value = "Text Box";
            // TextBoxField.Border = new Border(
            Border border = new Border(textBoxField);
            border.Width = 5;
            border.Dash = new Dash(1, 1);
            textBoxField.Border = border;
            textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
            // Add field to the document
            pdfDocument.Form.Add(textBoxField, 1);
            dataDir = dataDir + "TextBox_out.pdf";
            // Save modified PDF
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```