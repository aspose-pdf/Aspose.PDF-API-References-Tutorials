---
title: Get Value From Field
linktitle: Get Value From Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 140
url: /pdf/net/programming-with-forms/get-value-from-field/
---
### Sample source code for Get Value From Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
            // Get a field
            TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
            // Get field value
            Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
            Console.WriteLine("Value : {0} ", textBoxField.Value);
```