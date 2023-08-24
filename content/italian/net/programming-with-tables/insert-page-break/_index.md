---
title: Insert Page Break In PDF File
linktitle: Insert Page Break In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to insert a page break in PDF file using Aspose.PDF for .NET.
type: docs
weight: 110
url: /it/net/programming-with-tables/insert-page-break/
---
In this tutorial, we will learn how to insert a page break in PDF file using Aspose.PDF for .NET. We will explain the source code in C# step by step. At the end of this tutorial, you will know how to add a page break after a certain number of lines in a table of a PDF document. Let's start!

## Step 1: Setting up the environment
Make sure you have configured your C# development environment with Aspose.PDF for .NET. Add the reference to the library and import the necessary namespaces.

## Step 2: Creating the Document and Table
We create a new Document instance and add a page to this document. Next, we create a Table instance to represent our table in the PDF document. We also define the border styles for the table.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Step 3: Add rows to table
We use a loop to add 200 rows to the array. For each row, we create an instance of Row and add two cells with text content.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // When 10 lines are added, we insert a new page break
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Step 4: Adding the table to the document
We add the table to the paragraphs collection of the document page.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Step 5: Save the document
We save the PDF document with the page break inserted.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Example source code for Insert Page Break using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document instance
Document doc = new Document();
// Add page to pages collection of PDF file
doc.Pages.Add();
// Create table instance
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Set border style for table
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Set default border style for table with border color as Red
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Specify table columsn widht
tab.ColumnWidths = "100 100";
// Create a loop to add 200 rows for table
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// When 10 rows are added, render new row in new page
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Add table to paragraphs collection of PDF file
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Save the PDF document
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we learned how to insert a page break in a PDF document using Aspose.PDF for .NET. You can use this step-by-step guide to add a page break after a certain number of lines in a table in a PDF document using C#.

### FAQ's for insert page break in PDF file

#### Q: How can I change the page size for the new pages created after the page break?

A: To change the page size for the new pages created after the page break, you can set the `PageSize` property of the `Page` object. For example, you can use the following code to set the page size to A4:

```csharp
// Set the page size to A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Q: Can I control the page margins for the new pages after the page break?

A: Yes, you can control the page margins for the new pages after the page break. Use the `Margin` property of the `Page` object to set the page margins. For example, to set all margins to 10 points, you can use the following code:

```csharp
// Set all margins to 10 points
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Q: Is it possible to add headers and footers to the new pages after the page break?

A: Yes, you can add headers and footers to the new pages after the page break. Use the `Page.Header` and `Page.Footer` properties to add content to the header and footer sections of the page. For example:

```csharp
// Add header to the new pages
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Add footer to the new pages
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Q: Can I insert page breaks at specific locations other than after a certain number of rows?

A: Yes, you can insert page breaks at specific locations other than after a certain number of rows. You can set the `IsInNewPage` property of a row to `true` to force the table to start a new page after that row.

#### Q: How can I adjust the page break behavior based on content height?

A: You can use the `IsBroken` property of the table to enable or disable automatic row breaking across pages. When set to `true`, it allows rows to break across pages based on content height.