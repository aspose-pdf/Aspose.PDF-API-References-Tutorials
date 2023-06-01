---
title: Horizontally And Vertically Radio Buttons
linktitle: Horizontally And Vertically Radio Buttons
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 180
url: /pdf/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
### Sample source code for Horizontally And Vertically Radio Buttons using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
                // Load the previously saved document
                FormEditor formEditor = new FormEditor();
                formEditor.BindPdf(dataDir + "input.pdf");
                // RadioGap is distance between two radio button options. 
                formEditor.RadioGap = 4;
                // Add horizontal radio button
                formEditor.RadioHoriz = true;
                // RadioButtonItemSize if size of radio button item.
                formEditor.RadioButtonItemSize = 20;
                formEditor.Facade.BorderWidth = 1;
                formEditor.Facade.BorderColor = System.Drawing.Color.Black;
                formEditor.Items = new string[] { "First", "Second", "Third" };
                formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
                // Add other radio button situated vertically
                formEditor.RadioHoriz = false;
                formEditor.Items = new string[] { "First", "Second", "Third" };
                formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
                dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
                // Save the PDF document
                formEditor.Save(dataDir);
                Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```