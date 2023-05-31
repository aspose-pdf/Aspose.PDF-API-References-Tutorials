---
title: Set Border
linktitle: Set Border
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 200
url: /pdf/net/programming-with-tables/set-border/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
           
            // Instantiate Document object
            Document doc = new Document();
            // Add page to PDF document
            Page page = doc.Pages.Add();
            // Create BorderInfo object
            Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
            // Specify that Top border will be double
            border.Top.IsDoubled = true;
            // Specify that bottom border will be double
            border.Bottom.IsDoubled = true;
            // Instantiate Table object
            Aspose.Pdf.Table table = new Aspose.Pdf.Table();
            // Specify Columns width information
            table.ColumnWidths = "100";
            // Create Row object
            Aspose.Pdf.Row row = table.Rows.Add();
            // Add a Table cell to cells collection of row
            Aspose.Pdf.Cell cell = row.Cells.Add("some text");
            // Set the border for cell object (double border)
            cell.Border = border;
            // Add table to paragraphs collection of Page
            page.Paragraphs.Add(table);
            dataDir = dataDir + "TableBorderTest_out.pdf";
            // Save the PDF document
            doc.Save(dataDir);
            
            Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
            
        
```

