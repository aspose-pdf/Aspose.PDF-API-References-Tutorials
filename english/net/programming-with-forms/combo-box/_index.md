---
title: Combo Box
linktitle: Combo Box
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /pdf/net/programming-with-forms/combo-box/
---
### Sample source code for Combo Box using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
                // Create Document object
                Document doc = new Document();
                // Add page to document object
                doc.Pages.Add();
                // Instantiate ComboBox Field object
                ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
                // Add option to ComboBox
                combo.AddOption("Red");
                combo.AddOption("Yellow");
                combo.AddOption("Green");
                combo.AddOption("Blue");
                // Add combo box object to form fields collection of document object
                doc.Form.Add(combo);
                dataDir = dataDir + "ComboBox_out.pdf";
                // Save the PDF document
                doc.Save(dataDir);
                Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```