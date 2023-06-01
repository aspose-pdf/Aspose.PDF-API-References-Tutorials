---
title: Fill XFAFields
linktitle: Fill XFAFields
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /pdf/net/programming-with-forms/fill-xfafields/
---
### Sample source code for Fill XFAFields using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            // Load XFA form
            Document doc = new Document(dataDir + "FillXFAFields.pdf");
            // Get names of XFA form fields
            string[] names = doc.Form.XFA.FieldNames;
            // Set field values
            doc.Form.XFA[names[0]] = "Field 0";
            doc.Form.XFA[names[1]] = "Field 1";
            dataDir = dataDir + "Filled_XFA_out.pdf";
            // Save the updated document
            doc.Save(dataDir);
            Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```