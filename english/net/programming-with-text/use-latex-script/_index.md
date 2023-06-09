---
title: Use Latex Script
linktitle: Use Latex Script
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Latex script to add mathematical expressions or formulae in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 550
url: /net/programming-with-text/use-latex-script/
---

This tutorial explains how to use Latex script to add mathematical expressions or formulae in a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the steps to create a document, add a table with a cell containing LaTeX script, and save the document.

## Prerequisites

Before you begin, ensure that you have the following:

- Basic knowledge of C# programming language.
- Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or use NuGet to install it in your project.

## Step 1: Set up the project

Create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library.

## Step 2: Import necessary namespaces

Add the following using directives at the beginning of your C# file to import the required namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Tables;
using Aspose.Pdf.Text;
```

## Step 3: Create and configure the document

Create a new `Document` object and add a page to it:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Step 4: Create and configure the table

Create a table and add a row to it:

```csharp
Table table = new Table();
Row row = table.Rows.Add();
```

## Step 5: Add a cell with LaTeX script

Create a cell and add a `LatexFragment` containing the Latex script:

```csharp
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
```

Note that the `true` parameter in the `LatexFragment` constructor eliminates Latex paragraph indents.

## Step 6: Add the table to the page

Add the table to the page:

```csharp
page.Paragraphs.Add(table);
```

## Step 7: Save the document

Save the document to a PDF file:

```csharp
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

### Sample source code for Use Latex Script using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create a new Document Object
Document doc = new Document();
// Add Page in Pages Collection
Page page = doc.Pages.Add();
// Create a Table
Table table = new Table();
// Add a row into Table
Row row = table.Rows.Add();
// Add Cell with Latex Script to add methematical expressions/formulae
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
// Second LatexFragment constructor bool parameter provides LaTeX paragraph indents elimination.
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
// Add table inside page
page.Paragraphs.Add(table);
// Save the document
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

## Conclusion

Congratulations! You have successfully learned how to use Latex script to add mathematical expressions or formulae in a PDF document using Aspose.PDF for .NET. This tutorial provided step-by-step instructions on creating a document, adding a table with a cell containing LaTeX script, and saving the document. You can now incorporate this code into your own C# projects to generate PDF files with mathematical content.
