---
title: Remove Multiple Tables In PDF Document
linktitle: Remove Multiple Tables In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove multiple tables in PDF document using Aspose.PDF for .NET.
type: docs
weight: 150
url: /ru/net/programming-with-tables/remove-multiple-tables/
---
In this tutorial, we will guide you step by step to remove multiple tables in PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

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

### Example source code for Remove Multiple Tables using Aspose.PDF for .NET

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

### FAQ's for remove multiple tables in PDF document

#### Q: Can I remove specific tables instead of all tables in a PDF document?

A: Yes, you can remove specific tables instead of all tables in a PDF document using Aspose.PDF for .NET. In the provided example, all tables on the second page are removed. However, you can modify the code to target and remove specific tables based on your requirements. To do this, you need to identify the tables you want to remove and then call the `absorber.Remove(table)` method for each specific table you wish to delete.

#### Q: How can I remove tables from multiple pages in the PDF document?

A: To remove tables from multiple pages in the PDF document, you need to repeat the process for each page. In the provided example, the code removes tables only from the second page using `pdfDocument.Pages[1]`. To remove tables from other pages, you can use similar code for each desired page by replacing the page index (e.g., `pdfDocument.Pages[2]`, `pdfDocument.Pages[3]`, and so on).

#### Q: What happens if I try to remove a table that does not exist on the specified page?

A: If you try to remove a table that does not exist on the specified page, it will not result in an error. The `absorber.Remove(table)` method will simply ignore the removal request, and the PDF document will remain unchanged.

#### Q: Can I undo the removal of tables after saving the document?

A: No, once you save the modified PDF document after removing the tables, the changes are permanent, and you cannot undo the removal of tables. Therefore, it is essential to be cautious while removing content from a PDF document as the original data will be lost.

#### Q: Are there any restrictions on the type of tables that can be removed using this method?

A: The method shown in this tutorial allows you to remove tables from a PDF document without restrictions based on the content of the table. However, it is essential to consider the overall structure and layout of the document to ensure that removing tables does not negatively affect the remaining content and readability.