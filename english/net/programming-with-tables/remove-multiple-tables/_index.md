---
title: Remove Multiple Tables
linktitle: Remove Multiple Tables
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove multiple tables in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 150
url: /pdf/net/programming-with-tables/remove-multiple-tables/
---

In this tutorial, we will guide you step by step to remove multiple tables in a PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Loading the existing PDF document
First, you need to load the existing PDF document using the following code:

```csharp
// Path to the documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the existing PDF document
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Step 2: Creating the TableAbsorber object to find the tables
Next, we'll create a TableAbsorber object to find the tables in the PDF document:

```csharp
// Create a TableAbsorber object to find the tables
TableAbsorber absorber = new TableAbsorber();
```

## Step 3: Visit the second page with the absorber
We will now visit the second page of the PDF document using the absorber:

```csharp
// Visit the second page with the absorber
absorb.Visit(pdfDocument.Pages[1]);
```

## Step 4: Obtaining a copy of the table collection
To be able to drop the tables, we need to get a copy of the tables collection:

```csharp
// Get a copy of the table collection
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Step 5: Browse the copy of the collection and remove the tables
Now let's iterate through the copy of the collection of tables and remove them one by one:

```csharp
// Browse the copy of the collection and remove the tables
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Step 6: Saving the document
Finally, we save the modified PDF document:

```csharp
// Save the document
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Example source code for Remove Multiple Tables using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load existing PDF document
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Create TableAbsorber object to find tables
TableAbsorber absorber = new TableAbsorber();

// Visit second page with absorber
absorber.Visit(pdfDocument.Pages[1]);

// Get copy of table collection
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Loop through the copy of collection and removing tables
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Save document
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Conclusion
Congratulation ! You have now learned how to remove multiple tables in a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to upload the document, find the tables, and remove them. Now you can apply this knowledge to your own projects.
