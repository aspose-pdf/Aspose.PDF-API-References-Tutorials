---
title: Modify Form Field
linktitle: Modify Form Field
second_title: Aspose.PDF for .NET API Reference
description: Easily edit form fields in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 190
url: /net/programming-with-forms/modify-form-field/
---

In this tutorial, we will show you how to edit a form field in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document

Load the existing PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Step 3: Get the form field

Get the form field you want to edit:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Step 4: Change the field value

Change the form field value:

```csharp
textBoxField.Value = "New Value";
```

## Step 5: Edit Field Properties

Modify additional form field properties as needed. For example, you can make it read-only:

```csharp
textBoxField.ReadOnly = true;
```

## Step 6: Save the edited document

Save the modified PDF document:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Modify Form Field using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Get a field
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modify field value
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to edit a form field in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily navigate to a specific field, change its value, and adjust its properties as needed.
