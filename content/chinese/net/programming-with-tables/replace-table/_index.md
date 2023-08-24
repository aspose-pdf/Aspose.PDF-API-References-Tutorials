---
title: Replace Table In PDF Document
linktitle: Replace Table In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace a table in PDF document using Aspose.PDF for .NET.
type: docs
weight: 180
url: /zh/net/programming-with-tables/replace-table/
---
In this tutorial, we will guide you step by step to replace a table in PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Loading the existing PDF document
First, you need to load the existing PDF document using the following code:

```csharp
// Path to the documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the existing PDF document
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Step 2: Creating the TableAbsorber object to find the tables
Next, we'll create a TableAbsorber object to find the tables in the PDF document:

```csharp
// Create a TableAbsorber object to find the tables
TableAbsorber absorber = new TableAbsorber();
```

## Step 3: Visit the first page with the absorber
We will now visit the first page of the PDF document using the absorber:

```csharp
// Visit the first page with the absorber
absorb.Visit(pdfDocument.Pages[1]);
```

## Step 4: Getting the first table on the page
To be able to replace the table, we will obtain the first table of the page:

```csharp
// Get the first table on the page
AbsorbedTable table = absorb.TableList[0];
```

## Step 5: Creating a new table
Now we will create a new table with the desired columns and cells:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Step 6: Replacing the existing table with the new table
We will now replace the existing table with the new table on the first page of the document:

```csharp
// Replace the table with the new table
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Step 7: Saving the document
Finally, we save the modified PDF document:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Example source code for Replace Table using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load existing PDF document
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Create TableAbsorber object to find tables
TableAbsorber absorber = new TableAbsorber();

// Visit first page with absorber
absorber.Visit(pdfDocument.Pages[1]);

// Get first table on the page
AbsorbedTable table = absorber.TableList[0];

// Create new table
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Replace the table with new one
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Save document
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Conclusion
Congratulation ! You have now learned how to replace a table in a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to load the document, find the existing table, create a new table, and replace it. Now you can apply this knowledge to your own projects.

### FAQ's for replace table in PDF document

#### Q: Can I replace multiple tables in the same PDF document using this approach?

A: Yes, you can replace multiple tables in the same PDF document by following the same process for each table you want to replace. After obtaining the `AbsorbedTable` object for each table using the `TableAbsorber`, you can create corresponding new tables and then use the `absorber.Replace()` method to replace each existing table with the respective new table.

#### Q: What happens if the new table has a different number of columns than the original table?

A: If the new table has a different number of columns than the original table, it may result in unexpected behavior or layout issues in the modified PDF document. It is essential to ensure that the new table's structure (number of columns and their widths) matches the original table's structure for seamless replacement.

#### Q: Can I replace a table on a specific page other than the first page?

A: Yes, you can replace a table on a specific page other than the first page by changing the page index in the `pdfDocument.Pages[]` method call when obtaining the `AbsorbedTable` object. For example, to replace a table on the second page, you would use `pdfDocument.Pages[2]`.

#### Q: Can I customize the appearance of the new table, such as adding background color or borders?

A: Yes, you can customize the appearance of the new table by setting various properties of the `Table` and its cells. For example, you can set the `BackgroundColor` property of cells to add background color. You can also set the `DefaultCellBorder` property of the new table or individual cells to add borders.

#### Q: Does replacing a table affect the content layout of the rest of the PDF document?

A: Replacing a table may affect the content layout if the new table's size or structure differs significantly from the original table. The rest of the content on the page will reflow to accommodate the new table. It is essential to carefully design the new table to fit seamlessly within the existing layout to avoid any layout issues.