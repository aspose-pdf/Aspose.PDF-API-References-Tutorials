---
title: Fill Form Field
linktitle: Fill Form Field
second_title: Aspose.PDF for .NET API Reference
description: Easily fill out form fields in your PDF documents using Aspose.PDF for .NET.
type: docs
weight: 80
url: /net/programming-with-forms/fill-form-field/
---

In this tutorial, we will show you how to populate a form field using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

Open the existing PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Step 3: Get Field

Get the desired form field (in this example, we're using the "textbox1" field):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Step 4: Change the field value

Modify the field value with the desired value:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Step 5: Save the updated document

Save the updated PDF document:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Fill Form Field using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Get a field
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modify field value
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to populate a form field using Aspose.PDF for .NET. By following these steps, you can easily change form field values in your PDF documents using Aspose.PDF.
