---
title: Retrieve Form Field In Tab Order
linktitle: Retrieve Form Field In Tab Order
second_title: Aspose.PDF for .NET API Reference
description: Learn how to retrieve and modify form fields in tab order using Aspose.PDF for .NET. Step-by-step guide with code examples to streamline PDF form navigation.
type: docs
weight: 240
url: /net/programming-with-forms/retrieve-form-field-in-tab-order/
---
## Introduction

Managing PDF documents and ensuring they function as expected, especially with interactive fields, can sometimes feel like herding cats. But don’t worry, with the right tools, you can take control and make your PDFs work exactly how you want. In this guide, we’re diving into how to retrieve form fields in tab order using Aspose.PDF for .NET. This is an essential trick to streamline user experience, making sure form navigation is seamless. 

## Prerequisites

Before you dive into the code, let's make sure you have all the essentials set up:

- Aspose.PDF for .NET: You need the Aspose.PDF library installed in your project. If you don’t have it yet, download it [here](https://releases.aspose.com/pdf/net/).
- Development Environment: Set up a C# development environment like Visual Studio.
- .NET Framework: Ensure that .NET is installed on your system.
- PDF Document: Have a PDF document with form fields ready for testing.
  
Once these basics are in place, you're ready to retrieve and manipulate form fields in tab order like a pro.

## Import Packages

To work with Aspose.PDF, you’ll first need to import the necessary namespaces into your project. These namespaces give you access to all the functionality for manipulating PDFs.

```csharp
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

These are the core imports required for working with the PDF and its form fields.

## Step 1: Load the PDF Document

Before we can do anything with form fields, we need to load the PDF document. This is the starting point for all interactions with your PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
```

Here, we initialize the `Document` object by passing the path to the PDF we want to work with. Make sure the path points to the location where your document is stored.

## Step 2: Access the First Page

Next, we need to access the page that contains the form fields. For simplicity, we’re focusing on the first page, but you can modify this for any page in your document.

```csharp
Page page = doc.Pages[1];
```

This line fetches the first page of the PDF. If your form fields are spread across multiple pages, you can adjust the page index accordingly.

## Step 3: Retrieve Fields in Tab Order

Now comes the interesting part: retrieving the form fields based on their tab order. The `FieldsInTabOrder` property helps in fetching the fields in the order they should appear when the user navigates through the form using the Tab key.

```csharp
IList<Field> fields = page.FieldsInTabOrder;
```

This code gives us a list of fields, sorted according to their tab order.

## Step 4: Display Field Names

Once we have the fields, let’s output their names to see which fields are part of the form and their sequence.

```csharp
string s = "";
foreach (Field field in fields)
{
    s += field.PartialName + ", ";
}
```

Here, we loop through each field in the list and concatenate the `PartialName` of each field. The `PartialName` represents the name of the form field in the PDF document. This step is particularly useful for debugging or verifying the field names.

## Step 5: Modify Tab Order

Sometimes, you might want to change the tab order of the form fields to improve the user experience. For example, the form might require the first field to be third and the third to be first. Here’s how you can adjust the tab order:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

In this example, we’re changing the tab order of three fields in the form. You can adjust the `TabOrder` property to match your desired sequence.

## Step 6: Save the Modified PDF

Once you’ve updated the tab order, you’ll want to save the PDF with the changes. This is a critical step to ensure your modifications are reflected in the document.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

This saves the updated PDF to a new file. Always save it as a new file to avoid overwriting your original document.

## Step 7: Verify the Changes

After saving the PDF, it's a good idea to reopen the document and verify that the changes were applied correctly. Here’s how you can check the tab order after modification:

```csharp
Document doc1 = new Document(dataDir + "39522_out.pdf");
string index = "";
foreach (Field field in doc1.Form)
{
    index += field.TabOrder + ", ";
}
```

This code loads the updated document and outputs the new tab order for all fields. It ensures that your changes were successful.

---

## Conclusion

And there you have it! Retrieving and modifying form field tab order in PDF documents is not only manageable but also essential for creating a seamless user experience. Using Aspose.PDF for .NET, you can easily control how users navigate through your PDF forms, ensuring that everything works just as you expect.

## FAQ's

### Can I apply this method to multi-page PDF forms?  
Yes, you can. Simply access the specific page where the form fields are located and apply the same method.

### How do I install Aspose.PDF for .NET in my project?  
You can download the library from [here](https://releases.aspose.com/pdf/net/) and integrate it using NuGet in Visual Studio.

### Can I reorder fields on the same page?  
Absolutely! Just use the `TabOrder` property to customize the order of fields on any page.

### What happens if I don’t specify the tab order?  
If you don’t set the tab order explicitly, the fields will follow the default order based on how they were added to the PDF.

### Is it possible to programmatically add new form fields?  
Yes, Aspose.PDF allows you to create and add new form fields programmatically.
