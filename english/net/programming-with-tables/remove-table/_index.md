---
title: Remove Table
linktitle: Remove Table
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 160
url: /pdf/net/programming-with-tables/remove-table/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();

            // Load existing PDF document
            Document pdfDocument = new Document(dataDir + "Table_input.pdf");

            // Create TableAbsorber object to find tables
            TableAbsorber absorber = new TableAbsorber();

            // Visit first page with absorber
            absorber.Visit(pdfDocument.Pages[1]);

            // Get first table on the page
            AbsorbedTable table = absorber.TableList[0];

            // Remove the table
            absorber.Remove(table);

            // Save PDF
            pdfDocument.Save(dataDir + "Table_out.pdf");
            
        
```

