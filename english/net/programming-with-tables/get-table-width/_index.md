---
title: Get Table Width
linktitle: Get Table Width
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /pdf/net/programming-with-tables/get-table-width/
---



```csharp

            
            // Create a new document
            Document doc = new Document();
            // Add page in document
            Page page = doc.Pages.Add();
            // Initialize new table
            Table table = new Table
            {
                ColumnAdjustment = ColumnAdjustment.AutoFitToContent
            };
            // Add row in table 
            Row row = table.Rows.Add();
            // Add cell in table
            Cell cell = row.Cells.Add("Cell 1 text");
            cell = row.Cells.Add("Cell 2 text");
            // Get table width
            Console.WriteLine(table.GetWidth());
            
            System.Console.WriteLine("Extracted table width succesfully!");
        
```

