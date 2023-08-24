---
title: Set Border In PDF To Table
linktitle: Set Border In PDF To Table
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set a border in PDF to table with Aspose.PDF for .NET.
type: docs
weight: 200
url: /sv/net/programming-with-tables/set-border/
---
In this tutorial, we will guide you step by step to set a border in a table of a PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Instantiating the Document object
First, we'll instantiate a Document object:

```csharp
Document doc = new Document();
```

## Step 2: Adding a page to the PDF document
Next, we'll add a page to the PDF document:

```csharp
Page page = doc.Pages.Add();
```

## Step 3: Creating the BorderInfo object
We will now create a BorderInfo object to define the border of the table:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Step 4: Specifying top and bottom borders
We'll specify that the top and bottom borders will be double:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Step 5: Instantiating the Table object
Now let's instantiate a Table object:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Step 6: Specifying column widths
We will specify the widths of the columns of the table:

```csharp
table. ColumnWidths = "100";
```

## Step 7: Creating the Row Object
We will create a Row object:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Step 8: Adding a cell to the row
Next, we'll add a cell to the row:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Step 9: Setting the cell border
We are going to define the border of the cell (double border):

```csharp
cell. Border = border;
```

## Step 10: Adding the table to the page
Now let's add the table to the document page:

```csharp
page.Paragraphs.Add(table);
```

## Step 11: Save PDF document
Finally, we will save the PDF document:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Example source code for Set Border using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document object
Document doc = new Document();
// Add page to PDF document
Page page = doc.Pages.Add();
// Create BorderInfo object
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Specify that Top border will be double
border.Top.IsDoubled = true;
// Specify that bottom border will be double
border.Bottom.IsDoubled = true;
// Instantiate Table object
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Specify Columns width information
table.ColumnWidths = "100";
// Create Row object
Aspose.Pdf.Row row = table.Rows.Add();
// Add a Table cell to cells collection of row
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Set the border for cell object (double border)
cell.Border = border;
// Add table to paragraphs collection of Page
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Save the PDF document
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusion
Congratulation ! You have now learned how to set a border in a table of a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to create a document, add a page, configure the table border, and save the PDF document. Now you can apply this knowledge to your own projects.

### FAQ's

#### Q: Can I set different border styles (e.g., dashed or dotted) for the table's top and bottom borders?

A: Yes, you can set different border styles for the table's top and bottom borders by modifying the `border.Top.Style` and `border.Bottom.Style` properties in the provided C# source code. Aspose.PDF for .NET allows you to choose from various border styles, including Solid, Dashed, Dotted, Double, and more.

#### Q: How can I set the color of the table's border?

A: You can set the color of the table's border by modifying the `border.Color` property in the C# source code. Simply provide the desired color, such as `Aspose.Pdf.Color.Red` or any other valid color representation, to customize the border color.

#### Q: Is it possible to apply borders to individual cells within the table with different settings (e.g., different colors or border styles)?

A: Yes, you can apply borders to individual cells within the table with different settings by configuring the `cell.Border` property for each cell individually. This allows you to have cell-specific border styles and colors based on your requirements.

#### Q: Can I remove the border from specific sides of the table (e.g., left and right borders)?

A: Yes, you can remove the border from specific sides of the table by modifying the `border.Left`, `border.Right`, `border.Top`, and `border.Bottom` properties in the C# source code. Setting these properties to `null` will remove the border from the corresponding sides of the table.

#### Q: How can I adjust the thickness of the table's border?

A: You can adjust the thickness of the table's border by modifying the `border.Width` property in the C# source code. Simply set the desired border width (in points) to achieve the desired thickness.