---
title: Preserve Rights
linktitle: Preserve Rights
second_title: Aspose.PDF for .NET API Reference
description: Preserve form rights in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 210
url: /content/net/programming-with-forms/preserve-rights/
---

In this tutorial, we will show you how to preserve form rights in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the document

Open the source PDF document using a `FileStream` with read and write permission:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Step 3: Edit Form Fields

Go through all the form fields in the document and make the necessary changes. In this example, we're changing the value of a form field that has "A1" in its name:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Step 4: Save the updated document

Save the modified PDF document:

```csharp
pdfDocument.Save();
```

## Step 5: Close the `FileStream`

Don't forget to close the `FileStream` object when you're done:

```csharp
fs. Close();
```

### Sample source code for Preserve Rights using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Read the source PDF form with FileAccess of Read and Write.
// We need ReadWrite permission because after modification,
// We need to save the updated contents in same document/file.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instantiate Document instance
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Get values from all fields
foreach (Field formField in pdfDocument.Form)
{
	// If the fullname of field contains A1, perform the operation
	if (formField.FullName.Contains("A1"))
	{
		// Cast form field as TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Modify field value
		textBoxField.Value = "Testing";
	}
}
// Save the updated document in save FileStream
pdfDocument.Save();
// Close the File Stream object
fs.Close();
```

## Conclusion

In this tutorial, we learned how to preserve the rights of a form in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily access form fields and make specific changes while preserving access and write permissions.
