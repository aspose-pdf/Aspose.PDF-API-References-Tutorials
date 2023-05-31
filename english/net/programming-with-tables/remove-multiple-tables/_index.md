---
title: Remove Multiple Tables
linktitle: Remove Multiple Tables
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 150
url: /pdf/net/programming-with-tables/remove-multiple-tables/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();

            // Load existing PDF document
            Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

            // Create TableAbsorber object to find tables
            TableAbsorber absorber = new TableAbsorber();

            // Visit second page with absorber
            absorber.Visit(pdfDocument.Pages[1]);

            // Get copy of table collection
            AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
            absorber.TableList.CopyTo(tables, 0);

            // Loop through the copy of collection and removing tables
            foreach (AbsorbedTable table in tables)
                absorber.Remove(table);

            // Save document
            pdfDocument.Save(dataDir + "Table2_out.pdf");
            
        
```

