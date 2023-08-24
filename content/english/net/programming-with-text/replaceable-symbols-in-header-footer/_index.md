---
title: Replaceable Symbols In Header Footer
linktitle: Replaceable Symbols In Header Footer
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use replaceable symbols in the header and footer of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 320
url: /net/programming-with-text/replaceable-symbols-in-header-footer/
---
In this tutorial, we will explain how to use replaceable symbols in the header and footer of a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of creating a PDF, setting margins, adding header and footer with replaceable symbols, and saving the PDF using the provided C# source code.

## Prerequisites

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where you want to save the generated PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your desired directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a PDF Document and Page

Next, we create a new PDF document and add a page to it using the `Document` class and `Page` class from the Aspose.PDF library.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Step 3: Set Margins

We set the margins for the page using the `MarginInfo` class. Adjust the margin values according to your requirements.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Step 4: Add Header with Replaceable Symbols

We create a `HeaderFooter` object for the page and add a `TextFragment` with replaceable symbols to it.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Set text properties if desired
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Add more TextFragments or customize as needed
```

## Step 5: Add Footer with Replaceable Symbols

Similarly, we create a `HeaderFooter` object for the page footer and add `TextFragment` objects with replaceable symbols to it.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Add more TextFragments or customize as needed

hfFoot.Paragraphs.Add(tab2);
```

## Step 6: Save the PDF Document

Finally, we save the PDF document to the specified output file.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Sample source code for Replaceable Symbols In Header Footer using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Assign the marginInfo instance to Margin property of sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Instantiate a Text paragraph that will store the content to show as header
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Create a HeaderFooter object for the section
HeaderFooter hfFoot = new HeaderFooter();
// Set the HeaderFooter object to odd & even footer
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Add a text paragraph containing current page number of total number of pages
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Instantiate a table object
Table tab2 = new Table();
// Add the table in paragraphs collection of the desired section
hfFoot.Paragraphs.Add(tab2);
// Set with column widths of the table
tab2.ColumnWidths = "165 172 165";
// Create rows in the table and then cells in the rows
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Set the vertical allignment of the text as center alligned
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
// Sec1.Paragraphs.Add(New Text("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a#$NL" + "daily basis to ensure it contains the most up to date versions of each of our Java components. #$NL " + "Using Aspose.Total for Java developers can create a wide range of applications. #$NL #$NL #$NP" + "Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a#$NL" + "daily basis to ensure it contains the most up to date versions of each of our Java components. #$NL " + "Using Aspose.Total for Java developers can create a wide range of applications. #$NL #$NL #$NP" + "Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a#$NL" + "daily basis to ensure it contains the most up to date versions of each of our Java components. #$NL " + "Using Aspose.Total for Java developers can create a wide range of applications. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Add the table in paragraphs collection of the desired section
page.Paragraphs.Add(table);
// Set default cell border using BorderInfo object
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Set table border using another customized BorderInfo object
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Create rows in the table and then cells in the rows
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, you have learned how to use replaceable symbols in the header and footer of a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can create a PDF, set margins, add header and footer with replaceable symbols, and save the PDF.

### FAQ's

#### Q: What is the purpose of the "Replaceable Symbols In Header Footer" tutorial?

A: The "Replaceable Symbols In Header Footer" tutorial aims to guide you through the process of using the Aspose.PDF library for .NET to add replaceable symbols to the header and footer of a PDF document. Replaceable symbols allow you to dynamically replace specific placeholders with actual values when generating the PDF.

#### Q: What are replaceable symbols in the context of a PDF header and footer?

A: Replaceable symbols are placeholders that you can insert into the header and footer of a PDF document. These symbols act as dynamic placeholders for values that can be filled in at runtime, such as page numbers, dates, and custom information.

#### Q: Why would I want to use replaceable symbols in a PDF header and footer?

A: Replaceable symbols in the header and footer are useful when you want to include dynamic information in your PDF documents, such as page numbers, dates, or other variable data that may change when the document is generated.

#### Q: How can I set the margins for the PDF page?

A: You can set the margins for the PDF page using the `MarginInfo` class and assigning it to the `Margin` property of the `PageInfo` of the page. Adjust the margin values as needed.

#### Q: How do I add replaceable symbols to the header and footer?

A: You can add replaceable symbols by creating a `HeaderFooter` object for the header and footer of the page. Then, you can add `TextFragment` objects with the desired text, including replaceable symbols, to the `Paragraphs` collection of the `HeaderFooter` object.

#### Q: Can I customize the appearance of the replaceable symbols?

A: Yes, you can customize the appearance of the replaceable symbols by modifying the properties of the `TextFragment` objects that contain the symbols. You can set properties such as font, font size, color, alignment, and line spacing.

#### Q: What kind of replaceable symbols can I use?

A: You can use a variety of replaceable symbols, such as:

- `$p`: Current page number.
- `$P`: Total number of pages.
- `$d`: Current date.
- `$t`: Current time.
- Custom placeholders you define.

#### Q: Can I include other text and formatting around the replaceable symbols?

A: Yes, you can include other text and formatting around the replaceable symbols within the `TextFragment` objects. This allows you to create more complex headers and footers that incorporate dynamic and static content.

#### Q: How can I save the generated PDF document?

A: To save the generated PDF document, you can use the `Save` method of the `Document` class. Provide the desired output file path and name as an argument.

#### Q: Is a valid Aspose License required for this tutorial?

A: Yes, a valid Aspose License is required to execute the code successfully in this tutorial. You can obtain a full license or a 30-day temporary license from the Aspose website.
