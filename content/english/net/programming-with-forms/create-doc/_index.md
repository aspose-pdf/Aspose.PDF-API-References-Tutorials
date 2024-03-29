---
title: Create Document
linktitle: Create Document
second_title: Aspose.PDF for .NET API Reference
description: Easily create a document with radio buttons using Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-forms/create-doc/
---
In this tutorial, we will show you how to create a document with radio buttons using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

##Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a new document

Create a new Document object to hold the PDF document:

```csharp
Document doc = new Document();
```

## Step 3: Add a page

Add a new page to the document:

```csharp
Page page = doc.Pages.Add();
```

## Step 4: Add a radio button field

Create a radio button field and set its position and size:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Step 5: Add radio button options

Add the desired options to the radio button field. You can set the coordinates and size of each option as needed:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Step 6: Add the radio button field to the form

Add the radio button field to the Document Form Fields collection:

```csharp
doc.Form.Add(field);
```

## Step 7: Save the document

Save the PDF document:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Create Doc using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Create a new document
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Add radio button field
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Add radio button options. please note that these options are situated 
	// Neither horizontally nor vertically. 
	// You can try to set any coordinates (and even size) for them. 
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Save the PDF document
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to create a document with radio buttons using Aspose.PDF for .NET. By following these steps, you can easily add radio buttons to your PDF documents using Aspose.PDF.

### FAQ's

#### Q: Can I customize the appearance of the radio buttons in the document using Aspose.PDF for .NET?

A: Yes, you can customize the appearance of the radio buttons in the document using Aspose.PDF for .NET. You can set properties such as size, color, border style, and more to customize the appearance of the radio buttons.

#### Q: How can I add radio button groups with mutually exclusive options?

A: In order to create mutually exclusive options, you can add multiple radio button fields with the same name. This will ensure that when one option is selected, the other options with the same name will be automatically deselected.

#### Q: Is it possible to set a default selected option for the radio buttons?

A: Yes, you can set a default selected option for the radio buttons using Aspose.PDF for .NET. You can use the `Selected` property of the `RadioButtonOptionField` object to mark an option as selected by default.

#### Q: Can I add event handlers to the radio buttons?

A: Yes, you can add event handlers to the radio buttons using Aspose.PDF for .NET. You can associate JavaScript actions, such as `OnValueChanged`, to the radio buttons to perform specific actions when the user selects an option.

#### Q: How can I retrieve the selected option from the radio button group after the user makes a selection?

A: You can retrieve the selected option from the radio button group using Aspose.PDF for .NET. After the user makes a selection, you can access the `Selected` property of the `RadioButtonOptionField` object to check which option is selected.
