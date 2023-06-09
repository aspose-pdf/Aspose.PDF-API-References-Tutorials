---
title: Delete Form Field
linktitle: Delete Form Field
second_title: Aspose.PDF for .NET API Reference
description: Easily remove unwanted form fields from your PDF documents using Aspose.PDF for .NET.
type: docs
weight: 50
url: /content/net/programming-with-forms/delete-form-field/
---

In this tutorial, we will show you how to delete a form field using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

Open the existing PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Step 3: Delete a particular field

Delete a particular form field using its name:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Step 4: Save the edited document

Save the modified PDF document:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Delete Form Field using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Delete a particular field by name
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Save modified document
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to delete a form field using Aspose.PDF for .NET. By following these steps, you can easily remove unwanted form fields from your PDF documents using Aspose.PDF.