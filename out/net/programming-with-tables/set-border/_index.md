---
title: Set Border
linktitle: Set Border
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set a border in a PDF table with Aspose.PDF for .NET.
type: docs
weight: 200
url: /content/net/programming-with-tables/set-border/
---

In this tutorial, we will guide you step by step to set a border in a table of a PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Instantiating the Document object
First, we'll instantiate a Document object:

```csharp
Document doc = new Document();
```

## Step 2: Adding a page to the PDF document
Next, we'll add a page to the PDF document:

```csharp
Page page = doc.Pages.Add();
```

## Step 3: Creating the BorderInfo object
We will now create a BorderInfo object to define the border of the table:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Step 4: Specifying top and bottom borders
We'll specify that the top and bottom borders will be double:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Step 5: Instantiating the Table object
Now let's instantiate a Table object:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Step 6: Specifying column widths
We will specify the widths of the columns of the table:

```csharp
table. ColumnWidths = "100";
```

## Step 7: Creating the Row Object
We will create a Row object:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Step 8: Adding a cell to the row
Next, we'll add a cell to the row:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Step 9: Setting the cell border
We are going to define the border of the cell (double border):

```csharp
cell. Border = border;
```

## Step 10: Adding the table to the page
Now let's add the table to the document page:

```csharp
page.Paragraphs.Add(table);
```

## Step 11: Save PDF document
Finally, we will save the PDF document:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Example source code for Set Border using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

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

## Conclusion
Congratulation ! You have now learned how to set a border in a table of a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to create a document, add a page, configure the table border, and save the PDF document. Now you can apply this knowledge to your own projects.