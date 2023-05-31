---
title: Integrate With Database
linktitle: Integrate With Database
second_title: Aspose.PDF for .NET API Reference
description: Embed data from a database into a PDF document using Aspose.PDF for .NET.
type: docs
weight: 120
url: /pdf/net/programming-with-tables/integrate-with-database/
---

In this tutorial, we will learn how to embed data from a database into a PDF document using Aspose.PDF for .NET. We will explain the source code in C# step by step. At the end of this tutorial, you will know how to import table data from a database into a PDF document. Let's start!

## Step 1: Setting up the environment
Make sure you have configured your C# development environment with Aspose.PDF for .NET. Add the reference to the library and import the necessary namespaces.

## Step 2: Creating the DataTable
We create an instance of DataTable to represent the data we want to embed in the PDF document. In this example, we create a DataTable with three columns: Employee_ID, Employee_Name, and Gender. We also add two rows to the DataTable with dummy data.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Step 3: Creating the PDF Document and Table
We create an instance of Document and add a page to this document. Next, we create a Table instance to represent our table in the PDF document. We define table column widths and border styles.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Step 4: Importing data from the DataTable into the table
We use the ImportDataTable method to import the data from the DataTable into the table in the PDF document.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Step 5: Adding the table to the document
We add the table to the paragraphs collection of the document page.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Step 6: Save the document
We save the PDF document with the data from the embedded database.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Congratulations! You now know how to embed database data into a PDF document using Aspose.PDF for .NET.

### Example source code for Integrate With Database using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Add 2 rows into the DataTable object programmatically
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Create Document instance
Document doc = new Document();
doc.Pages.Add();
// Initializes a new instance of the Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Set column widths of the table
table.ColumnWidths = "40 100 100 100";
// Set the table border color as LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Set the border for table cells
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Add table object to first page of input document
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Save updated document containing table object
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we learned how to embed data from a database into a PDF document using Aspose.PDF for .NET. You can use this step-by-step guide to import the data from your own database and display them in PDF documents. Explore the Aspose.PDF documentation further to discover other features and possibilities offered by this powerful library.
