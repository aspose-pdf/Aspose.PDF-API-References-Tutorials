---
title: Grouped Check Boxes
linktitle: Grouped Check Boxes
second_title: Aspose.PDF for .NET API Reference
description: Easily create grouped checkboxes in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 170
url: /net/programming-with-forms/grouped-check-boxes/
---

In this tutorial, we will show you how to create grouped checkboxes in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Instantiate a Document Object

Instantiate a Document object:

```csharp
Document pdfDocument = new Document();
```

## Step 3: Add page to PDF document

Add a page to the PDF document:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Step 4: Instantiate a RadioButtonField Object

Instantiate a RadioButtonField object with the page number as argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Step 5: Add radio button options

Add radio button options using the RadioButtonOptionField object and specify their position using the Rectangle object:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Step 6: Customize radio button options

Customize radio button options by setting their style, border, and appearance:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Step 7: Add the radio buttons to the form

Add the radio buttons to the document form object:

```csharp
pdfDocument.Form.Add(radio);
```

## Step 8: Save the document

Save the PDF document:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Grouped Check Boxes using Aspose.Words for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantiate Document object
	Document pdfDocument = new Document();
	// Add a page to PDF file
	Page page = pdfDocument.Pages.Add();
	// Instatiate RadioButtonField object with page number as argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Add first radio button option and also specify its origin using Rectangle object
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Add radio button to form object of Document object
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Save the PDF document
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to create grouped checkboxes in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily add custom radio button options and bundle them in your PDF documents using Aspose.PDF.
