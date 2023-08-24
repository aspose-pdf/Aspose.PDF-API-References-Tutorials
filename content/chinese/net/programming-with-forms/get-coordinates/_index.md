---
title: Get PDF Form Field Coordinates
linktitle: Get PDF Form Field Coordinates
second_title: Aspose.PDF for .NET API Reference
description: Easily get PDF form field coordinates in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 120
url: /zh/net/programming-with-forms/get-coordinates/
---
In this tutorial, we will show you how to get PDF form field coordinates using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the output document

Load the output PDF document:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Step 3: Find added fields

Find the added form fields (in this example, we're using the "Item1", "Item2", and "Item3" fields):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Step 4: Display sub-item positions for each field

Cycle through the options for each field and view the coordinates for each sub-item:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Sample source code for Get Coordinates using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the output document 
	Document doc1 = new Document( dataDir + "input.pdf");
	// Find added fields
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// And show positions of sub items for each of them. 
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to get form field coordinates using Aspose.PDF for .NET. By following these steps, you can easily retrieve the coordinates of your form fields' sub-elements in your PDF documents using Aspose.PDF.

### FAQ's

#### Q: Can I use this method to get coordinates for any type of form field in Aspose.PDF for .NET?

A: Yes, you can use this method to get coordinates for various types of form fields in Aspose.PDF for .NET. The provided C# source code demonstrates how to get coordinates for RadioButton fields, but you can adapt the same approach for other form field types, such as TextBox, CheckBox, ListBox, and more.

#### Q: How can I modify or adjust the form field coordinates?

A: Form field coordinates are based on the PDF document's coordinate system, where the origin (0,0) is located at the bottom-left corner of the page. To modify or adjust the form field coordinates, you can update the `Rect` property of the respective form field or its sub-items, such as RadioButtonOptionField.

#### Q: Can I get the coordinates of form fields added programmatically to a PDF document?

A: Yes, you can get the coordinates of form fields that were added programmatically to a PDF document. Aspose.PDF for .NET allows you to add form fields dynamically, and once added, you can retrieve their coordinates using the approach demonstrated in this tutorial.

#### Q: What is the purpose of retrieving form field coordinates?

A: Retrieving form field coordinates can be helpful when you need to perform specific layout-related operations or validations on form fields within a PDF document. It allows you to accurately position and align form fields based on their coordinates, ensuring that they appear correctly in the document and provide a seamless user experience.

#### Q: Are the form field coordinates expressed in points or another unit?

A: The form field coordinates in Aspose.PDF for .NET are expressed in points. One point is equivalent to 1/72 inch, making it a standard unit of measurement in the PDF format.