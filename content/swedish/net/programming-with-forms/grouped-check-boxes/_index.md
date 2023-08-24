---
title: Grouped Check Boxes In PDF Document
linktitle: Grouped Check Boxes In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Easily create grouped checkboxes in PDF document with Aspose.PDF for .NET.
type: docs
weight: 170
url: /sv/net/programming-with-forms/grouped-check-boxes/
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

### Sample source code for Grouped Check Boxes using Aspose.PDF for .NET 
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

### FAQ's

#### Q: What are grouped checkboxes in a PDF document?

A: Grouped checkboxes in a PDF document refer to a set of radio button options that are grouped together. Radio buttons allow users to select only one option from a group of mutually exclusive choices. When one radio button is selected, the others in the same group are automatically deselected. This grouping behavior is useful when you want to present users with multiple options but limit their selection to one choice only.

#### Q: Can I customize the appearance of grouped checkboxes in Aspose.PDF for .NET?

A: Yes, you can customize the appearance of grouped checkboxes in Aspose.PDF for .NET. The API provides various options to set the style, border, and appearance of radio button options. You can define the position of each option, choose between different box styles (e.g., square, circle, cross), and adjust the border properties to achieve the desired visual representation.

#### Q: How do I add grouped checkboxes to a specific page in a PDF document?

A: To add grouped checkboxes to a specific page in a PDF document, you need to instantiate a `RadioButtonField` object with the desired page number as an argument. Then, create `RadioButtonOptionField` objects representing each radio button option and specify their position using the `Rectangle` object. Finally, add these options to the `RadioButtonField` and customize their appearance as needed before adding the `RadioButtonField` to the document form.

#### Q: Can I add multiple groups of checkboxes to a single PDF document?

A: Yes, you can add multiple groups of checkboxes to a single PDF document. Each group should have a unique `RadioButtonField` object, and the `RadioButtonOptionField` objects within each group should share the same page and unique names for their options. This ensures that the radio buttons within each group function correctly, and the selections are mutually exclusive.

#### Q: Are grouped checkboxes supported in all PDF viewers and applications?

A: Yes, grouped checkboxes are supported in all standard-compliant PDF viewers and applications. The PDF specification defines radio buttons and their grouping behavior, making them universally recognized in the PDF format. However, it's essential to test the functionality in different PDF viewers to ensure consistent behavior across various platforms.