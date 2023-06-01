---
title: Retrieve Form Field In Tab Order
linktitle: Retrieve Form Field In Tab Order
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 240
url: /pdf/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
### Sample source code for Retrieve Form Field In Tab Order using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
            Document doc = new Document(dataDir + "Test2.pdf");
            Page page = doc.Pages[1];
            IList<Field> fields = page.FieldsInTabOrder;
            string s = "";
            foreach (Field field in fields)
            {
                s += field.PartialName;
            }
            (doc.Form[3] as Field).TabOrder = 1;
            (doc.Form[1] as Field).TabOrder = 2;
            (doc.Form[2] as Field).TabOrder = 3;
            doc.Save(dataDir + "39522_out.pdf");
            Document doc1 = new Document(dataDir + "39522_out.pdf");
            s = "";
            foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
            {
                s += field.PartialName;
            }
            string index = "";
            foreach (Field field in doc1.Form)
            {
                index += field.TabOrder;
            }
```