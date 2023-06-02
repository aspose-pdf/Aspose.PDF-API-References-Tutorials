---
title: Determine Required Field
linktitle: Determine Required Field
second_title: Aspose.PDF for .NET API Reference
description: Easily determine required fields in your PDF forms using Aspose.PDF for .NET.
type: docs
weight: 60
url: /content/net/programming-with-forms/determine-required-field/
---

In this tutorial, we will show you how to determine the required fields of a PDF form using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load source PDF file

Load the source PDF file:

```csharp
Document pdf = new Document(dataDir + "DetermineRequiredField.pdf");
```

## Step 3: Instantiate the Form Object

Instantiate a Form object for the PDF:

```csharp
Aspose.Pdf.Facades.Form pdfForm = new Aspose.Pdf.Facades.Form(pdf);
```

## Step 4: Cycle through each form field

Go through each field of the PDF form:

```csharp
foreach(Field field in pdf.Form.Fields)
{
// Determine if the field is marked as required or not
bool isRequired = pdfForm.IsRequiredField(field.FullName);
if (isRequired)
{
// Display if the field is marked as required or not
Console.WriteLine("The field " + field.FullName + " is required");
}
}
```

### Sample source code for Determine Required Field using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load source PDF file
Document pdf = new Document(dataDir + "DetermineRequiredField.pdf");
// Instantiate Form object
Aspose.Pdf.Facades.Form pdfForm = new Aspose.Pdf.Facades.Form(pdf);
// Iterate through each field inside PDF form
foreach (Field field in pdf.Form.Fields)
{
	// Determine if the field is marked as required or not
	bool isRequired = pdfForm.IsRequiredField(field.FullName);
	if (isRequired)
	{
		// Print either the field is marked as required or not
		Console.WriteLine("The field named " + field.FullName + " is required");
	}
}
```

## Conclusion

In this tutorial, we learned how to determine the required fields of a PDF form using Aspose.PDF for .NET. By following these steps, you can easily check which fields are marked as required in your PDF form using Aspose.PDF.