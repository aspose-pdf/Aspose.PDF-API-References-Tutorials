---
title: Get Values From All Fields In PDF Document
linktitle: Get Values From All Fields In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Easily get the values of all form fields in PDF document with Aspose.PDF for .NET.
type: docs
weight: 150
url: /es/net/programming-with-forms/get-values-from-all-fields/
---
In this tutorial, we will show you how to get the values of all form fields in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the document

Open the PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Step 3: Get values for all fields

Loop through all the form fields in the document and get their names and values:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Sample source code for Get Values From All Fields using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Get values from all fields
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusion

In this tutorial, we learned how to get the values of all form fields in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily extract the values of all form fields from your PDF documents using Aspose.PDF.

### FAQ's

#### Q: Can I modify the values of form fields while retrieving them using Aspose.PDF for .NET?

A: Yes, you can modify the values of form fields while retrieving them using Aspose.PDF for .NET. Once you have the `Field` object representing a form field, you can update its `Value` property with the desired value. After making the necessary changes, you can save the updated PDF document to reflect the changes.

#### Q: How can I filter and retrieve specific form fields based on their types (e.g., text fields, checkboxes)?

A: To retrieve specific form fields based on their types, you can use conditional statements or LINQ queries to filter the fields of interest. You can check the type of each form field using the field's `FieldType` property, and then retrieve the values accordingly.

#### Q: What happens if the PDF document has no form fields?

A: If the PDF document does not contain any form fields, the `pdfDocument.Form` property will return an empty collection. In such cases, the loop to retrieve values will not execute, and no values will be displayed.

#### Q: Can I extract the form field values in a specific order or sort them alphabetically?

A: The order in which the form fields are retrieved depends on the underlying structure of the PDF document. Aspose.PDF for .NET returns the form fields in the order they were added to the document. If you want to display or process the form fields in a specific order, you can implement custom sorting logic based on your requirements.

#### Q: How can I handle encrypted PDF documents with password-protected form fields?

A: Aspose.PDF for .NET provides features to work with encrypted PDF documents and password-protected form fields. Before loading the document, you can set the password using the `pdfDocument.Password` property to access the secured PDF document and its form fields.