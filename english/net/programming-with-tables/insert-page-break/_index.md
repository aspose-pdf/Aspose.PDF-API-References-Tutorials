---
title: Insert Page Break
linktitle: Insert Page Break
second_title: Aspose.PDF for .NET API Reference
description: Learn how to insert a page break in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 110
url: /net/programming-with-tables/insert-page-break/
---

In this tutorial, we will learn how to insert a page break in a PDF document using Aspose.PDF for .NET. We will explain the source code in C# step by step. At the end of this tutorial, you will know how to add a page break after a certain number of lines in a table of a PDF document. Let's start!

## Step 1: Setting up the environment
Make sure you have configured your C# development environment with Aspose.PDF for .NET. Add the reference to the library and import the necessary namespaces.

## Step 2: Creating the Document and Table
We create a new Document instance and add a page to this document. Next, we create a Table instance to represent our table in the PDF document. We also define the border styles for the table.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Step 3: Add rows to table
We use a loop to add 200 rows to the array. For each row, we create an instance of Row and add two cells with text content.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // When 10 lines are added, we insert a new page break
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Step 4: Adding the table to the document
We add the table to the paragraphs collection of the document page.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Step 5: Save the document
We save the PDF document with the page break inserted.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Example source code for Insert Page Break using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document instance
Document doc = new Document();
// Add page to pages collection of PDF file
doc.Pages.Add();
// Create table instance
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Set border style for table
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Set default border style for table with border color as Red
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Specify table columsn widht
tab.ColumnWidths = "100 100";
// Create a loop to add 200 rows for table
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// When 10 rows are added, render new row in new page
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Add table to paragraphs collection of PDF file
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Save the PDF document
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we learned how to insert a page break in a PDF document using Aspose.PDF for .NET. You can use this step-by-step guide to add a page break after a certain number of lines in a table in a PDF document using C#.
