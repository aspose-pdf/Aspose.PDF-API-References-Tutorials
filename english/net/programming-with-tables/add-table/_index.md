---
title: Add Table
linktitle: Add Table
second_title: Aspose.PDF for .NET API Reference
description: Easily add tables to your PDF documents using Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-tables/add-table/
---

Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and transform PDF documents programmatically. In this tutorial, we will guide you through the process of adding a table to a PDF document using Aspose.PDF for .NET. We will explain each step of the code snippet provided and provide a comprehensive guide to help you understand and implement the functionality in your own projects.

## Introduction

PDF documents are widely used for sharing and preserving information in a portable format. Adding tables to PDF documents can enhance their visual appearance and make data presentation more organized and structured. Aspose.PDF for .NET provides a convenient way to add tables to existing PDF documents or create new ones from scratch.

## What is Aspose.PDF for .NET?

Aspose.PDF for .NET is a powerful and feature-rich library that enables .NET developers to create, manipulate, and convert PDF documents programmatically. It provides a wide range of functionalities, including creating PDF files from scratch, modifying existing PDF documents, merging or splitting PDF files, adding text, images, and tables, extracting data from PDFs, and much more. With Aspose.PDF for .NET, developers can automate complex PDF-related tasks and deliver high-quality PDF solutions.

## Adding a Table to a PDF Document

To add a table to a PDF document using Aspose.PDF for .NET, follow the step-by-step guide below:

## Step 1: Loading the source PDF document

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

The code snippet above loads the source PDF document that you want to add the table to. Make sure to provide the correct path to your PDF file.

## Step 2: Initializing a new instance of the Table

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

In this step, we create a new instance of the Table class, which represents a table in a PDF document.

## Step 3: Setting the table border color

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Here, we set the border color for the table using the BorderInfo class. You can customize the border style, width, and color according to your requirements.

## Step 4: Setting the border for table cells

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

We also set the border for table cells using the DefaultCellBorder property of the table object. This ensures that each cell in the table has the specified border style, width, and color.

## Step 5: Adding rows and cells to the table

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

In this step, we create a loop to add 10 rows to the table. Within each row, we add three cells with sample data. You can modify the code to add rows and cells according to your specific requirements.

## Step 6: Adding the table object to the document

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Save updated document containing table object
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Finally, we add the table object to the first page of the PDF document using the Paragraphs collection of the corresponding page.

### Example source code for add table using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load source PDF document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Initializes a new instance of the Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Set the table border color as LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Set the border for table cells
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Create a loop to add 10 rows
for (int row_count = 1; row_count < 10; row_count++)
{
	// Add row to table
	Aspose.Pdf.Row row = table.Rows.Add();
	// Add table cells
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Add table object to first page of input document
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Save updated document containing table object
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Conclusion

In this tutorial, we have explained the step-by-step process of adding a table to a PDF document using Aspose.PDF for .NET. We covered loading the source PDF document, initializing a new instance of the Table class, setting the table border color and cell borders, adding rows and cells to the table, and adding the table object to the document. By following this guide, you can easily incorporate tables into your PDF documents programmatically and customize them according to your specific needs.
