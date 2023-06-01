---
title: Get Values From All Fields
linktitle: Get Values From All Fields
second_title: Aspose.PDF for .NET API Reference
description: Easily get the values of all form fields in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 150
url: /pdf/net/programming-with-forms/get-values-from-all-fields/
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

### Sample source code for Get Values From All Fields using Aspose.Words for .NET 
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
