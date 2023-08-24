---
title: Create Table Element
linktitle: Create Table Element
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to create an array element with Aspose.PDF for .NET. Generate dynamic PDFs with tables easily.
type: docs
weight: 80
url: /ru/net/programming-with-tagged-pdf/create-table-element/
---
In this step-by-step guide, we'll walk you through the process of creating an array element using Aspose.PDF for .NET. Aspose.PDF is a powerful library that lets you manipulate PDF documents programmatically. Creating an array element is a common requirement when generating dynamic PDFs, and Aspose.PDF offers an easy and efficient way to accomplish this.

Let's dive into the code and learn how to create an array element using Aspose.PDF for .NET.

## Prerequisites

Before you begin, make sure you have the following:

1. Aspose.PDF library for .NET installed.
2. A basic knowledge of the C# programming language.

## Step 1: Setting up the environment

To get started, open your C# development environment and create a new project. Make sure you have added a reference to the Aspose.PDF library for .NET in your project.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the document

The first step is to create a new PDF document using the `Document` class.

```csharp
// Create the document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Here we also set the title and language for the tagged content.

## Step 3: Creating the array element

Next, we need to create the array element and add it to the document. We start by getting the root structure element, then we create a new table element using the `CreateTableElement` method.

```csharp
// Get the root structure element
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Save the tagged PDF document
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA compliance check
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Sample source code for Create Table Element using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Get root structure element
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Save Tagged Pdf Document
document.Save(dataDir + "CreateTableElement.pdf");

// Checking PDF/UA compliance
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

You have learned how to create an array element using Aspose.PDF for .NET. You can now generate PDF documents with dynamic tables using this method. Feel free to explore more features of Aspose.PDF to discover its full potential.

### FAQ's

#### Q: What is an array element in a PDF document, and why would I need to create one using Aspose.PDF for .NET?

A: An array element in a PDF document represents a structured collection of data, often used for creating tables or grids. You might need to create an array element using Aspose.PDF for .NET when generating dynamic PDFs that require structured data presentation, such as tabular information or grids.

#### Q: How does Aspose.PDF for .NET simplify the process of creating an array element?

A: Aspose.PDF for .NET provides a comprehensive set of classes and methods that allow you to create, customize, and manage array elements (tables) in a PDF document programmatically. This eliminates the need for manual PDF manipulation and streamlines the creation of structured data representations.

#### Q: What are the key steps involved in creating an array element using Aspose.PDF for .NET?

A: The key steps include setting up the environment, creating the document, obtaining the root structure element, creating a table element, defining rows and cells within the table, and specifying formatting and properties for the elements. The provided code example demonstrates these steps.

#### Q: What role does the `taggedContent` object play in creating an array element?

A: The `taggedContent` object, obtained from the document's `TaggedContent` property, allows you to define the structure of the tagged content within the PDF document. This includes creating and organizing array elements and their child elements in a hierarchical manner.

#### Q: How does the code ensure accessibility and semantics of the created array element?

A: The code sets attributes such as `AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment`, and `ColSpan` to enhance the accessibility and semantics of the array element. These attributes contribute to a well-structured, informative, and visually appealing representation of data.

#### Q: What is the significance of PDF/UA compliance in the context of creating array elements?

A: PDF/UA (Universal Accessibility) compliance ensures that the generated PDF documents are accessible to users with disabilities and meet certain accessibility standards. The code example checks PDF/UA compliance using the `Validate` method, helping you create documents that are inclusive and accessible.

#### Q: Can I customize the formatting and appearance of the array elements further?

A: Yes, you can customize the formatting and appearance of the array elements by adjusting attributes such as background color, border style, font size, and alignment. Aspose.PDF for .NET provides a wide range of properties to tailor the visual presentation to your requirements.

#### Q: How can I extend this knowledge to create more complex table structures or incorporate array elements into larger PDF documents?

A: You can extend this knowledge by exploring additional features of Aspose.PDF for .NET, such as merging multiple array elements, creating nested tables, adding headers and footers, and integrating array elements into larger PDF layouts. The library's documentation and examples provide guidance for these advanced scenarios.

#### Q: Is it possible to import data from external sources, such as databases or spreadsheets, to populate the array elements?

A: Yes, you can import data from external sources to populate array elements. You can use data retrieval and transformation techniques in C# to fetch data from databases, spreadsheets, or other sources and then populate the array elements accordingly.

#### Q: How can I use the knowledge gained from this tutorial to enhance the quality and usability of PDF documents I create programmatically?

A: The knowledge gained from this tutorial allows you to create structured and visually appealing array elements (tables) in PDF documents. By incorporating these techniques, you can improve the readability, accessibility, and user experience of dynamically generated PDFs, making them more informative and user-friendly.