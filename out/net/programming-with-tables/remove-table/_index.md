---
title: Remove Table
linktitle: Remove Table
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove a table in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 160
url: /content/net/programming-with-tables/remove-table/
---

In this tutorial, we will guide you step by step to remove a table in a PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

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

### Example source code for Remove Table using Aspose.Words for .NET

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