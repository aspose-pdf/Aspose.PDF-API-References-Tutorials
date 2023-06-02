---
title: Replace Table
linktitle: Replace Table
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace a table in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 180
url: /content/net/programming-with-tables/replace-table/
---

In this tutorial, we will guide you step by step to replace a table in a PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

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

### Example source code for Replace Table using Aspose.Words for .NET

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