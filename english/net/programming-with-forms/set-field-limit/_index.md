---
title: Set Field Limit
linktitle: Set Field Limit
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 260
url: /pdf/net/programming-with-forms/set-field-limit/
---
### Sample source code for Set Field Limit using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Adding Field with limit
            FormEditor form = new FormEditor();
            form.BindPdf( dataDir + "input.pdf");
            form.SetFieldLimit("textbox1", 15);
            dataDir = dataDir + "SetFieldLimit_out.pdf";
            form.Save(dataDir);
            Console.WriteLine("\nField added successfully with limit.\nFile saved at " + dataDir);
```