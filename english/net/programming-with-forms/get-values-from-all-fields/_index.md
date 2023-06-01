---
title: Get Values From All Fields
linktitle: Get Values From All Fields
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 150
url: /pdf/net/programming-with-forms/get-values-from-all-fields/
---
### Sample source code for Get Values From All Fields using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Open document
            Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
            // Get values from all fields
            foreach (Field formField in pdfDocument.Form)
            {
                Console.WriteLine("Field Name : {0} ", formField.PartialName);
                Console.WriteLine("Value : {0} ", formField.Value);
            }
```