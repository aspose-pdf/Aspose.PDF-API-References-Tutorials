---
title: Determine Table Break In PDF File
linktitle: Determine Table Break In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to determine table breaks in PDF file using Aspose.PDF for .NET.
type: docs
weight: 60
url: /fr/net/programming-with-tables/determine-table-break/
---
In this tutorial, we are going to learn how to determine table breaks in PDF file using Aspose.PDF for .NET. We will explain the source code in C# step by step. At the end of this tutorial, you will know how to determine if a table exceeds the page margins. Let's start!

## Step 1: Setting up the environment
First, make sure you've set up your C# development environment with Aspose.PDF for .NET. Add the reference to the library and import the necessary namespaces.

## Step 2: Creating the PDF document
In this step, we create a new `Document` object to represent the PDF document.

```csharp
pdf-Document = new Document();
```

This document will be used to add sections and tables.

## Step 3: Adding a section and a table
Now we are going to add a section to our PDF document and create a table inside this section.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

We also specify a top margin of 300 points for the table. You can adjust this value according to your needs.

## Step 4: Table Setup
In this step, we configure table properties, such as column widths and borders.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Here we define the width of the table columns and the cell borders. You can adjust these values according to your preferences.

## Step 5: Add rows and cells to the table
Now we will create rows and cells in the table using a loop.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Here we create 17 rows in the table and add three cells to each row. You can adjust the buckle according to your needs.

## Step 6: Determining Table Breaks
Now we will determine if the table exceeds the page margins by comparing the height of the page with the total height of the objects in the table.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

We calculate the height of the page and the total height of the objects taking into account the margins. If the difference is 10 or less, the table exceeds the page margins.

## Step 7: Saving the PDF document
Finally, we save the PDF document with the results.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Be sure to specify the correct document directory. The resulting PDF file will be saved with the determined table breaks.

### Example source code for Determine Table Break using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate an object PDF class
Document pdf = new Document();
// Add the section to PDF document sections collection
Aspose.Pdf.Page page = pdf.Pages.Add();
// Instantiate a table object
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Add the table in paragraphs collection of the desired section
page.Paragraphs.Add(table1);
// Set with column widths of the table
table1.ColumnWidths = "100 100 100";
// Set default cell border using BorderInfo object
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Set table border using another customized BorderInfo object
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Create MarginInfo object and set its left, bottom, right and top margins
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Set the default cell padding to the MarginInfo object
table1.DefaultCellPadding = margin;
// If you increase the counter to 17, table will break 
// Because it cannot be accommodated any more over this page
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Create rows in the table and then cells in the rows
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Get the Page Height information
float PageHeight = (float)pdf.PageInfo.Height;
// Get the total height information of Page Top & Bottom margin,
// Table Top margin and table height.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Display Page Height, Table Height, table Top margin and Page Top 
// And Bottom margin information
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Check if we deduct the sume of Page top margin + Page Bottom margin
// + Table Top margin and table height from Page height and its less
// Than 10 (an average row can be greater than 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// If the value is less than 10, then display the message. 
	// Which shows that another row can not be placed and if we add new 
	// Row, table will break. It depends upon the row height value.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Save the pdf document
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we learned how to determine table breaks in a PDF document using Aspose.PDF for .NET. You can use this step-by-step guide to check if a table exceeds the page margins in your own C# projects.

### FAQ's for determine table break in PDF file

#### Q: What is the purpose of determining table breaks in a PDF document?

A: The purpose of determining table breaks in a PDF document is to check if the table exceeds the page margins. This ensures that the table's content is correctly displayed within the available page space. By detecting table breaks, you can handle the content overflow and adjust the table layout accordingly.

#### Q: How can I adjust the top margin of the table?

A: In the provided C# source code, you can adjust the top margin of the table by modifying the value of the `table1.Margin.Top` property. Increase or decrease the value as needed to set the desired top margin for the table.

#### Q: Can I customize the appearance of the table, such as cell colors and font size?

A: Yes, you can customize the appearance of the table and its cells using various properties and methods provided by Aspose.PDF for .NET. For example, you can change cell background colors, font size, font family, text alignment, and more. Refer to the official documentation for more information on how to customize the table appearance.

#### Q: What happens if the table exceeds the page margins?

A: If the table exceeds the page margins, it may result in content truncation or overlapping, making the PDF document less readable and organized. By detecting table breaks and handling the overflow, you can ensure that the content remains properly displayed within the available page area.

#### Q: Can I determine table breaks for multiple tables in the same PDF document?

A: Yes, you can determine table breaks for multiple tables in the same PDF document. Simply repeat the steps for each table you want to analyze and adjust the table layout as necessary to prevent content overflow.