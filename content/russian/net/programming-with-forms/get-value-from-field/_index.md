---
title: Get Value From Field In PDF Document
linktitle: Get Value From Field In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Easily get the value of a form field in PDF document with Aspose.PDF for .NET.
type: docs
weight: 140
url: /ru/net/programming-with-forms/get-value-from-field/
---
In this tutorial, we will show you how to get the value of a form field using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the document

Open the PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Step 3: Get Field

Get the desired form field (in this example, we're using the "textbox1" field):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Step 4: Get field value

Get the field value using the `Value` property:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Sample source code for Get Value From Field using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Get a field
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Get field value
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusion

In this tutorial, we learned how to get the value of a form field using Aspose.PDF for .NET. By following these steps, you can easily extract the value of a specific form field in your PDF documents using Aspose.PDF.

### FAQ's

#### Q: Can I get the value of a form field without knowing its name beforehand?

A: No, you need to know the name or partial name of the form field to get its value using Aspose.PDF for .NET. The `pdfDocument.Form["fieldname"]` syntax requires the exact name or partial name of the form field to access its properties, including the value.

#### Q: What if the form field does not exist in the PDF document?

A: If the form field does not exist in the PDF document, the `pdfDocument.Form["fieldname"]` syntax will return `null`. It's essential to handle such cases by checking for `null` before accessing the properties of the form field to avoid exceptions.

#### Q: How can I handle different types of form fields (e.g., checkboxes, radio buttons) to get their values?

A: To handle different types of form fields, you can use the appropriate field classes available in Aspose.PDF for .NET. For example, use `CheckBoxField` to work with checkboxes and `RadioButtonField` to work with radio buttons. Once you have the correct field object, you can access its properties, including the value.

#### Q: Can I get the values of multiple form fields at once?

A: Yes, you can get the values of multiple form fields at once by iterating through the form fields collection using a loop or LINQ queries. This way, you can access the value of each form field in the PDF document programmatically.

#### Q: Is it possible to modify the value of a form field and save the changes back to the PDF document?

A: Yes, you can modify the value of a form field using Aspose.PDF for .NET and save the changes back to the PDF document. After updating the `Value` property of the form field, you can use the `pdfDocument.Save()` method to save the changes to the original PDF document.