---
title: Get Coordinates
linktitle: Get Coordinates
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /pdf/net/programming-with-forms/get-coordinates/
---
### Sample source code for Get Coordinates using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_Forms();
                // Load the output document 
                Document doc1 = new Document( dataDir + "input.pdf");
                // Find added fields
                RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
                RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
                RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
                // And show positions of sub items for each of them. 
                foreach (RadioButtonOptionField option in field0)
                {
                    Console.WriteLine(option.Rect);
                }
                foreach (RadioButtonOptionField option in field1)
                {
                    Console.WriteLine(option.Rect);
                }
                foreach (RadioButtonOptionField option in field2)
                {
                    Console.WriteLine(option.Rect);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```