---
title: Radio Button
linktitle: Radio Button
second_title: Aspose.PDF for .NET API Reference
description: Easily add radio buttons to your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 220
url: /it/net/programming-with-forms/radio-button/
---
In this tutorial, we will show you how to add a radio button in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Instantiate a Document Object

Instantiate a Document object to create a new PDF document:

```csharp
Document pdfDocument = new Document();
```

## Step 3: Add a page

Add a page to the PDF document:

```csharp
pdfDocument.Pages.Add();
```

## Step 4: Instantiate a RadioButtonField Object

Instantiate a RadioButtonField object specifying the page number as an argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Step 5: Add radio button options

Add radio button options to the RadioButtonField object by specifying the coordinates of each option with a Rectangle object:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Step 6: Add the radio button to the form

Add the radio button to the document's Form object:

```csharp
pdfDocument.Form.Add(radio);
```

## Step 7: Save the PDF Document

Save the created PDF document:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Radio Button using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantiate Document object
	Document pdfDocument = new Document();
	// Add a page to PDF file
	pdfDocument.Pages.Add();
	// Instatiate RadioButtonField object with page number as argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Add first radio button option and also specify its origin using Rectangle object
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Add second radio button option
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Add radio button to form object of Document object
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Save the PDF file
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to add a radio button in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily create a radio button and place it on a specific page in your PDF document.


### FAQ's

#### Q: Can I customize the appearance of the radio button, such as its size and color?

A: Yes, you can customize the appearance of the radio button using the `Rectangle` object's coordinates to define its size and position. Aspose.PDF for .NET allows you to adjust the radio button's appearance to suit your needs.

#### Q: Can I add multiple radio buttons with different groups on the same page?

A: Yes, you can add multiple radio buttons with different groups on the same page. Each group of radio buttons can have a unique name, and only one option within each group can be selected at a time.

#### Q: How can I add a label or text description to the radio button options?

A: To add a label or text description to the radio button options, you can use the `TextStamp` class from Aspose.PDF for .NET to overlay text on the PDF document at specific coordinates.

#### Q: Is Aspose.PDF for .NET compatible with all versions of .NET Framework?

A: Yes, Aspose.PDF for .NET is compatible with all versions of .NET Framework, including .NET Core and .NET Standard.

#### Q: Can I programmatically control the selection of a radio button option in the PDF document?

A: Yes, you can programmatically control the selection of a radio button option using the `IsSelected` property of the `RadioButtonOption` class. This property allows you to set a specific option as selected.