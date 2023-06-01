---
title: Set Java Script
linktitle: Set Java Script
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 270
url: /pdf/net/programming-with-forms/set-java-script/
---
### Sample source code for Set Java Script using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load input PDF file
            Document doc = new Document(dataDir + "SetJavaScript.pdf");
            TextBoxField field = (TextBoxField)doc.Form["textbox1"];
            // 2 digits after point
            // No separator
            // Neg style = minus
            // No currency
            field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
            field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
            // Set initial field value
            field.Value = "123";
            dataDir = dataDir + "Restricted_out.pdf";
            // Save resultant PDF
            doc.Save(dataDir);
            Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```