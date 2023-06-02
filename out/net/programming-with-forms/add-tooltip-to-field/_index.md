---
title: Add Tooltip To Field
linktitle: Add Tooltip To Field
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a tooltip to a field with Aspose.PDF for .NET.
type: docs
weight: 10
url: /content/net/programming-with-forms/add-tooltip-to-field/
---

Aspose.PDF for .NET is a powerful library that allows developers to manipulate PDF documents programmatically. In this tutorial, we will walk through the process of adding a tooltip to a field using Aspose.PDF for .NET. We will provide a step-by-step guide to help you understand and implement this functionality in your C# code.

## Step 1: Setting up the project and including Aspose.PDF for .NET

Before we begin, make sure you have Aspose.PDF for .NET installed in your development environment. You can download the library from the official website and follow the installation instructions provided.

Once you have installed Aspose.PDF for .NET, create a new C# project in your preferred Integrated Development Environment (IDE). Add a reference to the Aspose.PDF.dll file in your project to access the library's functionality.

## Step 2: Loading the source PDF form

In this step, we will load the source PDF form that contains the field to which we want to add a tooltip. First, ensure that you have the source PDF form file available in your project directory. You can obtain a sample PDF form or use your own existing form.

To load the PDF form, use the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load source PDF form
Document doc = new Document(dataDir + "AddTooltipToField.pdf");
```

Make sure to replace `"AddTooltipToField.pdf"` with the actual filename of your source PDF form.

## Step 3: Adding a tooltip to a text field

Now that we have loaded the source PDF form, we can proceed to add a tooltip to a specific text field. In this example, let's assume that the text field's name is "textbox1".

To add a tooltip to the text field, use the following code:

```csharp
// Set the tooltip for textfield
(doc.Form["textbox1"] as Field).AlternateName = "Text box tool tip";
```

Replace `"textbox1"` with the actual name of the text field to which you want to add the tooltip. Also, customize the tooltip text by modifying the value assigned to `AlternateName`.

## Step 4: Saving the updated document

After adding the tooltip to the field, we need to save the updated document. Specify the output file path where you want to save the modified PDF form.

To save the updated document, use the following code:

```csharp
dataDir = dataDir + "AddTooltipToField_out.pdf";
// Save the updated document
doc.Save(dataDir);
Console.WriteLine("\nTooltip added successfully.\nFile saved at " + dataDir);
```

Make sure to provide the desired output file name and path. After executing this code, the modified PDF form with the added tooltip will be saved to the specified location.

### Sample source code for Add Tooltip To Field using Aspose.Words for .NET 

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load source PDF form
Document doc = new Document(dataDir + "AddTooltipToField.pdf");
// Set the tooltip for textfield
(doc.Form["textbox1"] as Field).AlternateName = "Text box tool tip";
dataDir = dataDir + "AddTooltipToField_out.pdf";
// Save the updated document
doc.Save(dataDir);
Console.WriteLine("\nTooltip added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulations! You have successfully learned how to add a tooltip to a field using Aspose.PDF for .NET. By following the step-by-step guide in this tutorial, you can enhance your PDF forms with tooltips to provide additional information or guidance to the users. Remember to explore the documentation and examples provided by Aspose.PDF for .NET to discover more advanced features and functionalities offered by the library.