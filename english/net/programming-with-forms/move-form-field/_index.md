---
title: Move Form Field
linktitle: Move Form Field
second_title: Aspose.PDF for .NET API Reference
description: Easily move form fields around in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 200
url: /net/programming-with-forms/move-form-field/
---

In this tutorial, we will show you how to move a form field in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document

Load the existing PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Step 3: Get the form field

Get the form field you want to move:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Step 4: Change Field Location

Change the location of the form field by defining a new rectangular area:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Step 5: Save the edited document

Save the modified PDF document:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Move Form Field using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Get a field
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modify field location
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Save modified document
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to move a form field in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily navigate to a specific field and change its location as needed.
