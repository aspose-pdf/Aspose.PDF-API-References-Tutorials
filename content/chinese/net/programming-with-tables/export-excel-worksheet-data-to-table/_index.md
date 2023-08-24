---
title: Export Excel Worksheet Data To Table
linktitle: Export Excel Worksheet Data To Table
second_title: Aspose.PDF for .NET API Reference
description: Export data from an Excel sheet to a PDF table using Aspose.PDF for .NET.
type: docs
weight: 70
url: /zh/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
In this tutorial, we will learn how to export data from an Excel worksheet and create a table in a PDF document using the Aspose.PDF for .NET library. We will walk through the source code step by step and explain each section in detail. By the end of this tutorial, you will be able to generate PDF files with tables containing data from Excel worksheets. Let's get started!

## Requirements
Before we begin, make sure you have the following:

- Basic knowledge of C# programming language
- Visual Studio installed on your machine
- Aspose.PDF for .NET library added to your project

## Step 1: Setting up the Environment
To begin, create a new C# project in Visual Studio. Add the reference to the Aspose.PDF for .NET library by right-clicking on your project in the Solution Explorer, selecting "Manage NuGet Packages," and searching for "Aspose.PDF." Install the package and you're ready to go.

## Step 2: Loading the Excel Worksheet
In the first step of our code, we define the path to the directory containing the Excel document. Replace "YOUR DOCUMENT DIRECTORY" with the actual directory path where your Excel file is located.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Here, we use the Aspose.Cells library to load the Excel workbook. Make sure to replace "newBook1.xlsx" with the name of your Excel file.

## Step 3: Accessing the Worksheet
Next, we need to access the first worksheet in the Excel file. We do this using the `Worksheets` collection of the `Workbook` object.

```csharp
// Accessing the first worksheet in the Excel file
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

If your Excel file contains multiple worksheets, you can change the index value `[0]` to access a different worksheet.

## Step 4: Exporting Data to DataTable
Now, we will export the contents of the Excel worksheet to a `DataTable` object. We specify the range of cells to export using the `ExportDataTable` method.

```csharp
// Exporting the contents of 7 rows and 2 columns starting from 1st cell to DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In this example, we export all rows and columns starting from the first cell (0, 0) to the last cell in the worksheet. Set the appropriate range based on your requirements.

## Step 5: Creating a PDF Document
Now, we will create a new PDF document using the Aspose.PDF library.

```csharp
// Instantiate a Document instance
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

This creates an empty PDF document where we can add content.

## Step 6: Adding a Page and Table
To display the data in a table format, we need to add a page and a table to the PDF document.

```csharp
// Create a page in the document instance
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Create a Table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Add the Table object in the paragraphs collection of the section
sec1.Paragraphs.Add(tab1);
```

Here, we create a new page and a table object. We then add the table to the paragraphs collection of the page.

## Step 7: Setting Table Properties
Before importing the data, we need to set some properties of the table, such as column widths and default cell borders.

```csharp
// Set column widths of the table
tab1.ColumnWidths = "40 100 100";

// Set default cell border of the table using BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In this example, we set the column widths to 40, 100, and 100 units. Adjust the values based on your data. We also set the default cell border to display borders on all sides of each cell.

## Step 8: Importing Data to the Table
Now, we will import the data from the `DataTable` object into the table using the `ImportDataTable` method.

```csharp
// Import data into the Table object from the DataTable created above
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

Here, we specify the range of rows and columns to import. In this example, we import all rows and columns from the `dataTable` object.

## Step 9: Formatting the Table
To enhance the appearance of the table, we can apply formatting to specific cells or rows. In this step, we will format the first row and alternate rows of the table.

```csharp
// Get 1st row from the table
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Format the first row
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Set the background color of the cells in the first row
     curCell.BackgroundColor = Color.Blue;// Set the face for the cells in the first row
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Set the font color of the cells in the first row
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Set the text alignment for the cells in the first row
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternate row format
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Set the background color of the cells in alternate rows
         curCell.BackgroundColor = Color.Gray;
        
         // Set the text color of the cells in alternate rows
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Here, we iterate through the cells in the first row and set their background color, font face, font color, and text alignment. Then, we iterate through all cells in the alternate rows and set their background and text color.

## Step 10: Saving the PDF Document
Finally, we save the PDF document to the specified location.

```csharp
// Save the PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Make sure to replace "YOUR DOCUMENT DIRECTORY" with the desired directory path and filename for the output PDF file.

### Example source code for Export Excel Worksheet Data To Table using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Accessing the first worksheet in the Excel file
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exporting the contents of 7 rows and 2 columns starting from 1st cell to DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instantiate a Document instanc
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Create a page in the document instance
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Create a Table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Add the Table object in the paragraphs collection of the section
sec1.Paragraphs.Add(tab1);

// Set column widths of the table.  We need to specify the ColumnCount manually.
// As the curent excel worksheet has three columsn, so we are specifying the same count
tab1.ColumnWidths = "40 100 100";

// Set default cell border of the table using BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Import data into the Table object from the DataTable created above
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Get 1st row from the table
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Iterate through all cells in the 1st row and set their background color to blue
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Set the background of all the cells in 1st row of the table.
	curCell.BackgroundColor = Color.Blue;
	// Set the font face for the cells of 1st row in the table.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Set the font Color of all the cells in 1st row of the table.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Set the text allignment for the cells of 1st row as Center.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Iterate through all cells in the 1st row and set their background color to blue
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Set the background color of all the cells except of the 1st row.
		curCell.BackgroundColor = Color.Gray;
		// Set the Text color of all the cells except the 1st row.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Save the Pdf
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusion
In this tutorial, we learned how to export data from an Excel worksheet to a PDF table using the Aspose.PDF for .NET library. We covered the step-by-step process of loading the Excel worksheet, creating a PDF document, adding a table, importing data, andformatting the table. You can now generate PDF files with tables containing Excel data programmatically.

### FAQ's

#### Q: What is the purpose of exporting Excel worksheet data to a PDF table?

A: Exporting Excel worksheet data to a PDF table allows you to present the data in a structured and organized format. It enables you to generate PDF files with tables that contain data from Excel worksheets, making it easier to share and preserve information in a portable document format.

#### Q: Can I customize the appearance of the PDF table?

A: Yes, you can customize the appearance of the PDF table using various properties provided by Aspose.PDF for .NET. In the provided C# source code, you can modify the column widths, cell borders, text alignment, font style, and more to suit your specific requirements.

#### Q: How do I handle Excel files with multiple worksheets?

A: In the provided C# code, we accessed the first worksheet in the Excel file using the index `[0]`. If your Excel file contains multiple worksheets, you can access them by changing the index value accordingly, such as `[1]` for the second worksheet or `[2]` for the third worksheet.

#### Q: Can I apply different formatting to specific rows or cells in the PDF table?

A: Yes, you can apply different formatting to specific rows or cells in the PDF table. In the provided C# source code, we demonstrated how to format the first row and alternate rows differently by changing their background color, font style, and font color. You can apply similar formatting techniques to any specific rows or cells as needed.

#### Q: Is Aspose.PDF for .NET the only library that allows exporting Excel data to a PDF table?

A: Aspose.PDF for .NET is a powerful library for working with PDF documents in .NET applications. While there might be other libraries available, Aspose.PDF for .NET offers a wide range of features and capabilities for generating, manipulating, and exporting PDF files with tables from Excel data, making it a popular choice for such tasks.