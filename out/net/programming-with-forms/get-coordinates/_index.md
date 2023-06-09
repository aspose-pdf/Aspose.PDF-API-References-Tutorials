---
title: Get Coordinates
linktitle: Get Coordinates
second_title: Aspose.PDF for .NET API Reference
description: Easily get form field coordinates in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 120
url: /content/net/programming-with-forms/get-coordinates/
---

In this tutorial, we will show you how to get form field coordinates using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

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