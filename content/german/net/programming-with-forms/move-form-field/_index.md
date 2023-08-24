---
title: Move Form Field
linktitle: Move Form Field
second_title: Aspose.PDF for .NET API Reference
description: Easily move form fields around in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 200
url: /de/net/programming-with-forms/move-form-field/
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

### Sample source code for Move Form Field using Aspose.PDF for .NET 
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


### FAQ's

#### Q: Can I move multiple form fields within a single PDF document using Aspose.PDF for .NET?

A: Yes, you can move multiple form fields within a single PDF document using Aspose.PDF for .NET. Simply repeat the process for each form field you want to relocate.

#### Q: Will moving a form field affect its associated data or functionality?

A: No, moving a form field does not affect its associated data or functionality. The form field retains all its properties and values after being moved to a new location.

#### Q: How can I determine the exact coordinates for the new location of the form field?

A: You can specify the new location using the `Aspose.Pdf.Rectangle` class, where you define the X and Y coordinates of the top-left corner and the X and Y coordinates of the bottom-right corner of the rectangular area.

#### Q: Is Aspose.PDF for .NET compatible with both Windows and Linux environments?

A: Yes, Aspose.PDF for .NET is compatible with both Windows and Linux environments, providing flexibility for developers to work in their preferred operating systems.