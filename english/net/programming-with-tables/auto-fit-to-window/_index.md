---
title: Auto Fit To Window
linktitle: Auto Fit To Window
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 50
url: /pdf/net/programming-with-tables/auto-fit-to-window/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();

            // Instntiate the Pdf object by calling its empty constructor
            Document doc = new Document();
            // Create the section in the Pdf object
            Page sec1 = doc.Pages.Add();

            // Instantiate a table object
            Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
            // Add the table in paragraphs collection of the desired section
            sec1.Paragraphs.Add(tab1);

            // Set with column widths of the table
            tab1.ColumnWidths = "50 50 50";
            tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

            // Set default cell border using BorderInfo object
            tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

            // Set table border using another customized BorderInfo object
            tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
            // Create MarginInfo object and set its left, bottom, right and top margins
            Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
            margin.Top = 5f;
            margin.Left = 5f;
            margin.Right = 5f;
            margin.Bottom = 5f;

            // Set the default cell padding to the MarginInfo object
            tab1.DefaultCellPadding = margin;

            // Create rows in the table and then cells in the rows
            Aspose.Pdf.Row row1 = tab1.Rows.Add();
            row1.Cells.Add("col1");
            row1.Cells.Add("col2");
            row1.Cells.Add("col3");
            Aspose.Pdf.Row row2 = tab1.Rows.Add();
            row2.Cells.Add("item1");
            row2.Cells.Add("item2");
            row2.Cells.Add("item3");

            dataDir = dataDir + "AutoFitToWindow_out.pdf";
            // Save updated document containing table object
            doc.Save(dataDir);
            
                      
        
```

