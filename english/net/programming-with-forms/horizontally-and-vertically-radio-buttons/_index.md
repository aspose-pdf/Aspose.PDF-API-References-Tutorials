---
title: Horizontally And Vertically Radio Buttons
linktitle: Horizontally And Vertically Radio Buttons
second_title: Aspose.PDF for .NET API Reference
description: Easily create horizontal and vertical radio buttons in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 180
url: /net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

In this tutorial, we will show you how to create horizontally and vertically arranged radio buttons in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document

Load the existing PDF document:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Step 3: Customize radio button options

Customize radio button options by setting the following properties:

```csharp
formEditor. RadioGap = 4; // Distance between two radio button options
formEditor. RadioHoriz = true; // Horizontal layout of radio buttons
formEditor.RadioButtonItemSize = 20; // Size of radio buttons
formEditor.Facade.BorderWidth = 1; // Width of radio button border
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Radio button border color
```

## Step 4: Add Horizontal Radio Buttons

Add radio buttons arranged horizontally by specifying the options and position of the field:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Step 5: Add vertical radio buttons

Add radio buttons arranged vertically by specifying the options and position of the field:

```csharp
formEditor. RadioHoriz = false; // Vertical layout of radio buttons
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Step 6: Save the document

Save the modified PDF document:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Sample source code for Horizontally And Vertically Radio Buttons using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the previously saved document
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap is distance between two radio button options. 
	formEditor.RadioGap = 4;
	// Add horizontal radio button
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize if size of radio button item.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Add other radio button situated vertically
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Save the PDF document
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to create horizontally and vertically arranged radio buttons in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily customize the layout of radio buttons and add them to your PDF documents using Aspose.PDF.
