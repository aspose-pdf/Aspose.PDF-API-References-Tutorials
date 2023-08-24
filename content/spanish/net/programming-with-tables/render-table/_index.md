---
title: Render Table In PDF Document
linktitle: Render Table In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Learn how to display a table in PDF document using Aspose.PDF for .NET.
type: docs
weight: 170
url: /es/net/programming-with-tables/render-table/
---
In this tutorial, we will guide you step by step to display a table in PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Creating the document
First, we'll create a new PDF document:

```csharp
// Path to the documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a new document
Document doc = new Document();
```

## Step 2: Configuring page margins and orientation
Next, we'll configure the page margins and set the orientation to landscape mode:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Step 3: Creating the table and columns
Now let's create a table and set the column widths:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Step 4: Add rows and cells to the table
Next, we'll add rows and cells to the table using a loop:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Step 5: Adding the table to the page
Now let's add the table to the document page:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Step 6: Displaying the table on a new page
Next, we'll create a new table and set the "IsInNewPage" property to "true" to display the table on a new page:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Step 7: Save PDF
Finally, we save the PDF document:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Example source code for Render Table using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Added page.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// I want to keep table 1 to next page please...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusion
Congratulation ! You have now learned how to display a table in a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to create a document, configure page margins and orientation, add a table, and display a table on a new page. Now you can apply this knowledge to your own projects.

### FAQ's for render table in PDF document

#### Q: How can I modify the table's appearance, such as changing cell colors or adding borders?

A: To modify the table's appearance, you can set various properties of the `Aspose.Pdf.Table` and its cells. For example, you can set the `BackgroundColor` property of cells to change their background color. You can also set the `Border` property of the table or individual cells to add borders. Additionally, you can customize the font, text color, and alignment of the table content by modifying the `TextState` of the `TextFragment` objects added to the cells.

#### Q: Can I add headers or footers to the table?

A: Yes, you can add headers or footers to the table by creating additional rows at the beginning or end of the table and setting the appropriate content in the cells. You can customize the headers or footers independently from the rest of the table content by adding different styles or content to these specific rows.

#### Q: How can I control the table's position on the page?

A: To control the table's position on the page, you can adjust the `MarginInfo` of the `PageInfo` object. The `MarginInfo` allows you to set the left, right, top, and bottom margins of the page, which affects the available space for the table. You can also use the `PositioningType` property of the `Aspose.Pdf.Table` to control its horizontal and vertical alignment within the page's content area.

#### Q: Can I export the table to different file formats, such as Excel or CSV?

A: Aspose.PDF for .NET is primarily designed for working with PDF documents. While it can export the PDF document as an image or XPS, it does not directly support exporting tables to formats like Excel or CSV. To export the table data to different file formats, you may need to use additional libraries or methods to convert the PDF content to the desired format.

#### Q: How can I add hyperlinks to the table cells?

A: To add hyperlinks to the table cells, you can use the `Aspose.Pdf.WebHyperlink` class to create a hyperlink and then add it as an anchor to the `TextFragment` inside the cell. This allows you to associate a URL or link target with specific text or content within the cell, creating clickable hyperlinks.