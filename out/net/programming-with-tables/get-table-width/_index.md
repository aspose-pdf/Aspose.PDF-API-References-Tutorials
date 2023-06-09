---
title: Get Table Width
linktitle: Get Table Width
second_title: Aspose.PDF for .NET API Reference
description: Learn how to get the width of a table in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 90
url: /content/net/programming-with-tables/get-table-width/
---

In this tutorial, we are going to learn how to get the width of a table in a PDF document using Aspose.PDF for .NET. We will explain the source code in C# step by step. At the end of this tutorial, you will know how to get the width of a table in a PDF document. Let's start!

## Step 1: Setting up the environment
First, make sure you've set up your C# development environment with Aspose.PDF for .NET. Add the reference to the library and import the necessary namespaces.

## Step 2: Creating a New Document and Page
We create a new PDF document and add a page in this document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Step 3: Initializing a new table
We initialize a new table and set the column fit to "AutoFitToContent".

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## Step 4: Add row and cells in table
We add a row in the table and add cells in that row.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## Step 5: Get table width
We use the "GetWidth()" method to get the width of the table.

```csharp
Console.WriteLine(table.GetWidth());
```

### Example source code for get Table Width using Aspose.PDF for .NET

```csharp
// Create a new document
Document doc = new Document();
// Add page in document
Page page = doc.Pages.Add();
// Initialize new table
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// Add row in table 
Row row = table.Rows.Add();
// Add cell in table
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// Get table width
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## Conclusion
In this tutorial, we learned how to get the width of a table in a PDF document using Aspose.PDF for .NET. You can use this step-by-step guide to get table widths in your own C# projects.