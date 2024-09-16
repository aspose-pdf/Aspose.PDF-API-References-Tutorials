---
title: Export Excel Worksheet Data To Table
linktitle: Export Excel Worksheet Data To Table
second_title: Aspose.PDF for .NET API Reference
description: Learn how to export Excel worksheet data to a PDF table using Aspose.PDF for .NET. Step-by-step tutorial with code examples, prerequisites, and helpful tips.
type: docs
weight: 70
url: /net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Introduction

Have you ever needed to export data from an Excel worksheet into a PDF file, neatly arranged into a table format? Imagine having a bunch of data in Excel, but needing to share it as a professional-looking PDF. It can sound complicated, right? But with Aspose.PDF for .NET, you can turn this task into a breeze. In this tutorial, we'll walk you through the process of exporting Excel worksheet data into a table inside a PDF document using Aspose.PDF for .NET. We’ll take you step by step, breaking down everything so that even if you’re new to this, you’ll feel like a pro by the end.

## Prerequisites

Before we dive into the coding, let’s get a few things set up:

1. Aspose.PDF for .NET Library – Make sure you have the latest version installed. You can [download it here](https://releases.aspose.com/pdf/net/).
2. Aspose.Cells for .NET Library – You’ll need this to handle Excel operations. Download it from [here](https://releases.aspose.com/cells/net/).
3. .NET Development Environment – A tool like Visual Studio will work perfectly for coding.
4. Excel File – Have an Excel file with the data you want to export ready.

If you don’t have the Aspose.PDF and Aspose.Cells libraries, you can start with a [free trial](https://releases.aspose.com/).

## Import Packages

To begin with, ensure you've installed both Aspose.PDF and Aspose.Cells libraries in your project. You can install them using NuGet Package Manager in Visual Studio.

Here’s how to import the necessary packages in your C# code:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Now that the prerequisites are set, let’s walk through the process of exporting data from an Excel sheet to a table in a PDF document.

## Step 1: Load the Excel Workbook

To start, you need to load your Excel workbook into the program. In this step, we’ll use Aspose.Cells to open the Excel file.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load the Excel workbook
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Explanation: Here, we specify the directory path where our Excel file is located and load the workbook using `Aspose.Cells.Workbook`. Make sure to adjust `"YOUR DOCUMENT DIRECTORY"` to point to your file’s location.

## Step 2: Access the First Worksheet

After loading the workbook, we need to access the first worksheet where our data is stored.

```csharp
// Accessing the first worksheet in the Excel file
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Explanation: This step is straightforward—we grab the first worksheet from the workbook, which contains the data to be exported.

## Step 3: Export Data to DataTable

Now, let's export the data from the Excel sheet into a DataTable object, which will act as an intermediary for transferring the data to the PDF.

```csharp
// Exporting the contents of 7 rows and 2 columns starting from the 1st cell to DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Explanation: The `ExportDataTable` method extracts the data starting from the first cell of the worksheet and spans all rows and columns. This data is then stored in a `DataTable` for further use.

## Step 4: Create a New PDF Document

Next, we need to create a new PDF document using Aspose.PDF.

```csharp
// Instantiate a Document instance
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Create a page in the document instance
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Explanation: Here, we initialize a new `Aspose.Pdf.Document` and add a page to it. This page will later contain the table we’re creating from the Excel data.

## Step 5: Create a Table Object in PDF

Let’s move on to creating a table inside the PDF document.

```csharp
// Create a Table object
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Add the Table object to the paragraphs collection of the page
page.Paragraphs.Add(table);
```

Explanation: We create an `Aspose.Pdf.Table` object and add it to the paragraphs collection of the page, which ensures that the table gets displayed on the page.

## Step 6: Set Column Widths and Borders

Tables in PDF need defined column widths. We’ll also add borders to make the table more readable.

```csharp
// Set column widths of the table
table.ColumnWidths = "40 100 100";

// Set default cell border
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Explanation: We set the widths of the three columns and give all cells a default border with a thickness of `0.1F`.

## Step 7: Import Data from DataTable into PDF Table

Now, it's time to import the data from the DataTable into our PDF table.

```csharp
// Import data into the Table object from the DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

Explanation: The `ImportDataTable` method transfers all the data from the `DataTable` to the PDF table. This populates the table with the data from your Excel sheet.

## Step 8: Style the Header Row

Let’s style the header row of the table by changing the background color, font, and alignment.

```csharp
// Get the first row from the table
Aspose.Pdf.Row headerRow = table.Rows[0];

// Set styling for the header row
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Explanation: We loop through all cells in the first row (header) and set their background color to blue, text color to yellow, and align the text to the center.

## Step 9: Style the Remaining Rows

To differentiate between the header and the rest of the rows, let’s add a different style for the remaining rows.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Explanation: For all rows except the header, we set a gray background and white text color.

## Step 10: Save the PDF Document

Finally, save the PDF document with the table.

```csharp
// Save the Pdf
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Explanation: We save the PDF to the specified directory. Voilà! Your Excel data is now inside a beautifully formatted PDF table.

## Conclusion

And there you have it! In just a few steps, you've exported data from an Excel worksheet into a table inside a PDF using Aspose.PDF for .NET. By breaking down the process and styling it along the way, you can customize your output and ensure your data looks clean and professional. So the next time someone hands you an Excel file and asks for a PDF report, you know exactly what to do.

## FAQ's

### Can I customize the table more?
Absolutely! You can modify colors, fonts, alignment, and even add borders to specific cells.

### Is Aspose.PDF for .NET free?
It offers a free trial, but for extended use, you’ll need a license. You can [buy it here](https://purchase.aspose.com/buy).

### Can I export only specific rows and columns?
Yes, you can modify the parameters in the `ExportDataTable` method to export specific ranges.

### Does this work with large Excel files?
Yes, Aspose.Cells is designed to handle large Excel files efficiently.

### How can I add more pages to the PDF?
You can use `pdfDocument.Pages.Add()` to add as many pages as you need.
