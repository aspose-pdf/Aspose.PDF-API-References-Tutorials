---
title: Select Radio Button
linktitle: Select Radio Button
second_title: Aspose.PDF for .NET API Reference
description: Learn how to select a radio button in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 250
url: /content/net/programming-with-forms/select-radio-button/
---

Here is a detailed tutorial on how to select a radio button using Aspose.PDF for .NET. Follow these steps:

## Step 1: Start by defining the directory of your documents by specifying the path in the `dataDir` variable.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document using the `Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Step 3: Get the radio button field from the document form.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Step 4: Specify the index of the radio button to select from the group.

```csharp
radioField. Selected = 2;
```

## Step 5: Set the output path for the edited PDF file.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Step 6: Save the modified PDF file.

```csharp
pdfDocument.Save(dataDir);
```

## Step 7: Display a confirmation message and the location of the saved file.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Sample source code for Select Radio Button using Aspose.Words for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Open document
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Get a field
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Specify the index of radio button from group
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Save the PDF file
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to select a radio button using Aspose.PDF for .NET. By following the steps outlined above, you can manipulate and modify radio buttons in your PDF documents using Aspose.PDF for .NET.