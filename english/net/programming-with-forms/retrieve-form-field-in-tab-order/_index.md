---
title: Retrieve Form Field In Tab Order
linktitle: Retrieve Form Field In Tab Order
second_title: Aspose.PDF for .NET API Reference
description: Learn how to retrieve form fields in tab order using Aspose.PDF for .NET.
type: docs
weight: 240
url: /net/programming-with-forms/retrieve-form-field-in-tab-order/
---

When working with PDF documents in C# using Aspose.PDF for .NET, you may come across a scenario where you need to retrieve form fields in a specific tab order. This can be useful when you want to perform operations on form fields based on their tab sequence. In this tutorial, we will guide you step by step on how to retrieve form fields in tab order using Aspose.PDF for .NET.

## Requirements

Before we begin, make sure you have the following prerequisites:

- Visual Studio installed on your system
- Aspose.PDF for .NET library installed

Now, let's dive into the steps to retrieve form fields in tab order.

## Step 1: Setting the Document Directory

To start with, you need to set the document directory where your PDF document is located. You can do this by specifying the path to the directory in the `dataDir` variable.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 2: Loading the PDF Document

In this step, we will load the PDF document using Aspose.PDF for .NET. The `Document` class provides the ability to load and manipulate PDF documents.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

Here, `"Test2.pdf"` is the name of the PDF document you want to load. Make sure the document is present in the specified document directory.

## Step 3: Retrieving Form Fields in Tab Order

To retrieve form fields in tab order, we need to access the `FieldsInTabOrder` property of the `Page` class. This property returns a list of form fields sorted by their tab sequence.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

In the above code snippet, we retrieve the form fields from the second page (`doc.Pages[1]`) and iterate through each field to concatenate their partial names into the `s` variable. You can modify this code snippet based on your specific requirements.

## Step 4: Modifying the Tab Order

If you want to modify the tab order of form fields, you can do so by accessing the `TabOrder` property of each field and assigning a new tab order value. Here's an example:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

In the above code snippet, we assign new tab order values to three form fields (`doc.Form[3]`, `doc.Form[1]`, and `doc.Form[2]`). Adjust the field indices and tab order values according to your specific requirements.

## Step 5: Saving the Modified Document

After modifying the tab order of form fields, you need to save the modified document. You can do this using the `Save` method of the `Document` class.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

Here, `"39522_out.pdf"` is the name of the output file where the modified document will be saved. Specify the desired name and location for the output file.

### Sample source code for Retrieve Form Field In Tab Order using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Conclusion

In this tutorial, we learned how to retrieve form fields in tab order using Aspose.PDF for .NET. We covered the steps involved in loading a PDF document, retrieving form fields in tab order, modifying the tab order, and saving the modified document. By following these steps, you can efficiently work with form fields and customize their tab sequence as per your requirements.
