---
title: Manipulate Table In PDF File
linktitle: Manipulate Table In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily manipulate tables in PDF file with Aspose.PDF for .NET.
type: docs
weight: 130
url: /de/net/programming-with-tables/manipulate-table/
---
In this tutorial, we will walk you through the step-by-step process of manipulating tables in PDF file using Aspose.PDF for .NET. Tables are a common element in PDF documents, and being able to modify their content programmatically can be highly beneficial in various scenarios. We will use the C# source code provided to demonstrate the process.

## Requirements

Before we begin, make sure you have the following:

- Visual Studio or any other C# development environment installed.
- Aspose.PDF for .NET library added as a reference to your project.

Now, let's dive into the steps required to manipulate tables in a PDF document using Aspose.PDF for .NET.

## Step 1: Loading the PDF Document

The first step is to load the existing PDF document into your C# application. You need to provide the path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Replace "YOUR DOCUMENT DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 2: Finding Tables in the Document

To manipulate tables, we need to find them within the PDF document. Aspose.PDF for .NET provides a TableAbsorber class that allows us to extract tables from the document. We will create an instance of the TableAbsorber class and visit the desired page of the document.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

In this example, we are visiting the first page of the document. You can change the page number as per your requirements.

## Step 3: Accessing Table Cells and Text Fragments

Once we have the tables, we can access their cells and text fragments for manipulation. In the provided source code, we are accessing the first table, the first cell of its first row, and the second text fragment within that cell.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

You can modify the code to target different tables, cells, or text fragments based on your specific needs.

## Step 4: Manipulating Table Text

With the text fragment accessed, we can now modify its content. In the given example, we are changing the text to "hi world".

```csharp
fragment.Text = "hi world";
```

Feel free to replace "hi world" with your desired text.

## Step 5: Saving the Modified Document

Once the desired modifications are made, we need to save the modified PDF document.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Ensure you provide the path and filename for the modified document.


### Example source code for Manipulate Table using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Load existing PDF file
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Create TableAbsorber object to find tables
	TableAbsorber absorber = new TableAbsorber();

	// Visit first page with absorber
	absorber.Visit(pdfDocument.Pages[1]);

	// Get access to first table on page, their first cell and text fragments in it
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Change text of the first text fragment in the cell
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we have learned how to manipulate tables in a PDF document using Aspose.PDF for .NET. By following the step-by-step guide, you can easily load a PDF document, find tables, access cells and text fragments, modify table content, and save the modified document. This approach provides flexibility and efficiency when dealing with table manipulation in PDF documents.

### FAQ's for manipulate table in PDF file

#### Q: Can I manipulate tables in multi-page PDF documents?

A: Yes, you can manipulate tables in multi-page PDF documents using Aspose.PDF for .NET. In the provided example, we visited the first page of the document (`pdfDocument.Pages[1]`), but you can loop through all the pages and manipulate tables on each page as needed.

#### Q: How can I add new rows or columns to an existing table?

A: To add new rows or columns to an existing table, you can use the APIs provided by Aspose.PDF for .NET. You can access the `RowList` and `CellList` properties of the `TableAbsorber.TableList` to add new rows and cells programmatically. Refer to the Aspose.PDF for .NET documentation for detailed information and code examples.

#### Q: Is it possible to remove a table from a PDF document?

A: Yes, you can remove a table from a PDF document using Aspose.PDF for .NET. To achieve this, you can remove the specific `Table` object from the `Page.Paragraphs` collection. You can identify the table to remove by using properties like `Table.NumberOfColumns`, `Table.NumberOfRows`, and other unique identifiers.

#### Q: Can I change the formatting (font, color, alignment) of the table text?

A: Yes, you can change the formatting of the table text using Aspose.PDF for .NET. You can access the `TextState` property of the `TextFragment` object to modify the font, font size, color, and alignment of the text.

#### Q: Does Aspose.PDF for .NET support working with tables in PDF forms (AcroForms)?

A: Yes, Aspose.PDF for .NET supports working with tables in PDF forms (AcroForms). You can access and manipulate table elements in PDF forms similar to the approach demonstrated in this tutorial. Aspose.PDF for .NET provides extensive support for working with AcroForms and form fields.