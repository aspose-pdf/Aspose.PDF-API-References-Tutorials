---
title: Add Tooltip To Field
linktitle: Add Tooltip To Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /pdf/net/programming-with-forms/add-tooltip-to-field/
---
### Sample source code for Add Tooltip To Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load source PDF form
            Document doc = new Document(dataDir + "AddTooltipToField.pdf");
            // Set the tooltip for textfield
            (doc.Form["textbox1"] as Field).AlternateName = "Text box tool tip";
            dataDir = dataDir + "AddTooltipToField_out.pdf";
            // Save the updated document
            doc.Save(dataDir);
            Console.WriteLine("\nTooltip added successfully.\nFile saved at " + dataDir);
```