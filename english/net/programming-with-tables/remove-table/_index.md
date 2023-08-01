---
title: Remove Table In PDF Document
linktitle: Remove Table In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove a table in PDF document using Aspose.PDF for .NET.
type: docs
weight: 160
url: /net/programming-with-tables/remove-table/
---
In this tutorial, we will guide you step by step to remove a table in PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Loading the existing PDF document
First, you need to load the existing PDF document using the following code:

```csharp
// Path to the documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the existing PDF document
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
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
To be able to remove the table, we will obtain the first table of the page:

```csharp
// Get the first table on the page
AbsorbedTable table = absorb.TableList[0];
```

## Step 5: Deleting the table
Now let's remove the table using the absorber:

```csharp
// remove the table
absorb.Remove(table);
```

## Step 6: Save PDF
Finally, we save the modified PDF document:

```csharp
// Save the PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Example source code for Remove Table using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load existing PDF document
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Create TableAbsorber object to find tables
TableAbsorber absorber = new TableAbsorber();

// Visit first page with absorber
absorber.Visit(pdfDocument.Pages[1]);

// Get first table on the page
AbsorbedTable table = absorber.TableList[0];

// Remove the table
absorber.Remove(table);

// Save PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Conclusion
Congratulation ! You have now learned how to remove a table in a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to load the document, find the table, and remove it. Now you can apply this knowledge to your own projects.

### FAQ's for remove table in PDF document

#### Q: Can I remove multiple tables from a PDF document using this method?

A: No, the provided example code is designed to remove only one table from the PDF document. If you want to remove multiple tables, you need to modify the code accordingly. One approach is to loop through the `absorb.TableList` and remove each table one by one. However, keep in mind that removing multiple tables may require additional logic and considerations to avoid unintended consequences.

#### Q: What happens if the specified page does not contain any tables?

A: If the specified page does not contain any tables, the code will throw an `IndexOutOfRangeException` when attempting to access `absorb.TableList[0]`. To avoid this issue, you should check if `absorb.TableList` contains any elements before accessing the table.

#### Q: Can I remove tables from pages other than the first page?

A: Yes, you can remove tables from pages other than the first page by changing the page index in `pdfDocument.Pages[1]`. For example, to remove a table from the second page, use `pdfDocument.Pages[2]`.

#### Q: Will removing a table affect the layout and formatting of the remaining content in the PDF document?

A: Yes, removing a table will impact the layout and formatting of the remaining content in the PDF document. When a table is removed, the content below the table may shift up to fill the empty space. This can lead to changes in the overall appearance of the document. It is essential to consider the document's structure and layout before removing any table.

#### Q: Can I undo the removal of a table after saving the document?

A: No, once you save the modified PDF document after removing a table, the changes are permanent, and you cannot undo the removal of the table. Therefore, it is crucial to make backups of your original documents before performing any modifications to ensure data integrity.
