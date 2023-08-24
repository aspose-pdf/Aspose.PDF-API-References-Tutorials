---
title: Style Table Row
linktitle: Style Table Row
second_title: Aspose.PDF for .NET API Reference
description: Learn how to customize table rows with Aspose.PDF for .NET step by step guide to styling and formatting rows.
type: docs
weight: 180
url: /ru/net/programming-with-tagged-pdf/style-table-row/
---
In this detailed tutorial, we will walk you through the provided C# source code step by step to format the table row using Aspose.PDF for .NET. Follow the instructions below to understand how to customize table row styles and properties.

## Step 1: Setting up the environment

Before you begin, make sure you've configured your development environment to use Aspose.PDF for .NET. This includes installing the Aspose.PDF library and configuring your project to reference it.

## Step 2: Creating a document

In this step, we will create a new document object Aspose.PDF.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

We have created a new document and set the document title and language.

## Step 3: Obtaining the root structure element

In this step we will get the root structure element for our document.

```csharp
// Obtain the root structure element
StructureElement rootElement = taggedContent.RootElement;
```

We got the root structure element which will serve as a container for the array element.

## Step 4: Creating the array structure element

Now let's create a new table structure element for our document.

```csharp
// Create the array structure element
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

We have created a new array structure element and added it to the root structure element.

## Step 5: Customize table row styles and properties

In this step, we will customize the table row styles and properties.

```csharp
// Customize table row styles and properties
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

// Create the table header row
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// Customize the rows of the body of the table
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Create the footer line of the table
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

We've customized various aspects of the table row, such as background color, borders, row height, pagination, default cell style, and more.

## Step 6: Saving the tagged PDF document

Now that we've created our document with the styled table row, we'll save it as a tagged PDF document.
```csharp
// Save the tagged PDF document
document.Save(dataDir + "StyleTableRow.pdf");
```

We saved the tagged PDF document in the specified directory.

## Step 7: PDF/UA compliance validation

Next, we will validate the PDF/UA conformity of our document.

```csharp
// PDF/UA compliance check
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We uploaded the tagged PDF document and validated its PDF/UA compliance by generating an XML report.


### Sample source code for Style Table Row using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Get root structure element
StructureElement rootElement = taggedContent.RootElement;

// Create table structure element
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Save Tagged Pdf Document
document.Save(dataDir + "StyleTableRow.pdf");

// Checking PDF/UA compliance
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

In this tutorial, we learned how to format table row with Aspose.PDF for .NET. We customized the table row styles and properties, added the headers, body rows, and footer, saved the tagged PDF document, and validated its PDF/UA compliance.

### FAQ's

#### Q: What is the purpose of this tutorial on formatting table rows using Aspose.PDF for .NET?

A: The purpose of this tutorial is to guide you through the process of formatting table rows in a PDF document using Aspose.PDF for .NET. It provides step-by-step instructions and C# source code examples to help you customize table row styles and properties.

#### Q: What are the prerequisites for following this tutorial?

A: Before you start, ensure that you have set up your development environment to use Aspose.PDF for .NET. This involves installing the Aspose.PDF library and configuring your project to reference it.

#### Q: How can I create a new PDF document and set its title and language using Aspose.PDF for .NET?

A: To create a new PDF document, you need to create a `Document` object from the Aspose.PDF library. The tutorial's provided C# source code demonstrates how to create a document and set its title and language properties.

#### Q: What is the significance of the root structure element in a PDF document?

A: The root structure element acts as a container for other structure elements, helping to organize and categorize the content of the PDF document. It plays a crucial role in establishing the logical structure of the document.

#### Q: How do I create and customize a table structure element to format table rows using Aspose.PDF for .NET?

A: The tutorial explains how to create a table structure element and customize its properties to format table rows. It covers aspects such as background color, borders, row height, pagination, default cell style, and more.

#### Q: Can I customize the styles and properties of individual cells within a table row?

A: Yes, you can customize the styles and properties of individual cells within a table row. The tutorial demonstrates how to set properties such as background color, borders, text color, padding, and more for table cells within the formatted table row.

#### Q: How can I add headers, body rows, and a footer to the formatted table row?

A: The tutorial provides examples of creating and adding headers, body rows, and a footer to the table structure element. These elements can be customized further using the properties described in the tutorial.

#### Q: What is PDF/UA compliance, and how can I validate it for my tagged PDF document?

A: PDF/UA compliance ensures that the PDF document conforms to accessibility standards, making it more accessible to users with disabilities. The tutorial demonstrates how to validate PDF/UA conformity using the `Validate()` method and generate an XML compliance report.

#### Q: How can I incorporate these concepts into my own .NET applications?

A: You can use the provided C# source code examples as a guide to implementing table row formatting in your own .NET applications. Modify and adapt the code to match your requirements and integrate it into your projects.

#### Q: Are there any recommended best practices for formatting table rows in PDF documents?

A: When formatting table rows, consider the readability and accessibility of the content. Ensure that colors have sufficient contrast, use clear and legible fonts, and maintain a consistent layout. Validate PDF/UA compliance to ensure accessibility standards are met.

#### Q: What other features of Aspose.PDF for .NET can I explore for PDF document customization?

A: Aspose.PDF for .NET offers a wide range of features for PDF document customization, including text manipulation, image insertion, form field management, digital signatures, annotations, and more. Consult the official documentation and resources to explore additional functionalities.