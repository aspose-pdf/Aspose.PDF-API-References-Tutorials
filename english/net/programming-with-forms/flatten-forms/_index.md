---
title: Flatten Forms
linktitle: Flatten Forms
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /pdf/net/programming-with-forms/flatten-forms/
---
### Sample source code for Flatten Forms using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load source PDF form
            Document doc = new Document(dataDir + "input.pdf");
            // Flatten Forms
            if (doc.Form.Fields.Count() > 0)
            {
                foreach (var item in doc.Form.Fields)
                {
                    item.Flatten();
                }
            }
            dataDir = dataDir + "FlattenForms_out.pdf";
            // Save the updated document
            doc.Save(dataDir);
            Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```