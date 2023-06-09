---
title: Set Field Limit
linktitle: Set Field Limit
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set a field boundary in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 260
url: /content/net/programming-with-forms/set-field-limit/
---

Here is a detailed tutorial on how to set a field boundary using Aspose.PDF for .NET. Follow these steps:

## Step 1: Start by defining the directory of your documents by specifying the path in the `dataDir` variable.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Add the field with a boundary using the `FormEditor` class.

```csharp
FormEditor form = new FormEditor();
form.BindPdf(dataDir + "input.pdf");
form.SetFieldLimit("textbox1", 15);
```

## Step 3: Set the output path for the edited PDF file.

```csharp
dataDir = dataDir + "SetFieldLimit_out.pdf";
```

## Step 4: Save the modified PDF file.

```csharp
form.Save(dataDir);
```

## Step 5: Display a confirmation message and the location of the saved file.

```csharp
Console.WriteLine("\nField added successfully with limit.\nFile saved to location: " + dataDir);
```

### Sample source code for Set Field Limit using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Adding Field with limit
FormEditor form = new FormEditor();
form.BindPdf( dataDir + "input.pdf");
form.SetFieldLimit("textbox1", 15);
dataDir = dataDir + "SetFieldLimit_out.pdf";
form.Save(dataDir);
Console.WriteLine("\nField added successfully with limit.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to set a field boundary using Aspose.PDF for .NET. By following the steps outlined above, you can manipulate and set limits for form fields in your PDF documents using Aspose.PDF for .NET.