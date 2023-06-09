---
title: Get Value From Field
linktitle: Get Value From Field
second_title: Aspose.PDF for .NET API Reference
description: Easily get the value of a form field in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 140
url: /net/programming-with-forms/get-value-from-field/
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
