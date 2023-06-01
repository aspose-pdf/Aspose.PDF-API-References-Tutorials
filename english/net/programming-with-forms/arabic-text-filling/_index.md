---
title: Arabic Text Filling
linktitle: Arabic Text Filling
second_title: Aspose.PDF for .NET API Reference
description: Easily populate PDF form fields with Arabic text using Aspose.PDF for .NET.
type: docs
weight: 20
url: /pdf/net/programming-with-forms/arabic-text-filling/
---

In this tutorial, we are going to learn how to populate a PDF form field with Arabic text using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows developers to programmatically manipulate PDF documents. We'll walk you through the process step by step, explaining the C# source code required to accomplish this task.

## Step 1: Load PDF Form Content

First, we need to load the PDF form that contains the field we want to fill. We start by defining the path to the directory where the form is located:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Next, we create a `FileStream` object to read and write the form file:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

Next, we instantiate a `Document` object using the stream that contains the form file:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Step 2: Access the TextBoxField field

To fill the form field with Arabic text, we need to access the specific `TextBoxField` field that we want to fill. In this example, we assume the field name is "textbox1". We can retrieve the field reference using the `Form` property of the `pdfDocument` object:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Step 3: Fill the form field with Arabic text

Now that we have the `TextBoxField` reference, we can assign the Arabic text to its `Value` property:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Step 4: Save the updated document

Finally, we save the updated document to a new file:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

We also display a message to indicate the success of filling in the Arabic text:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Sample source code for Arabic Text Filling using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load PDF form contents
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instantiate Document instance with stream holding form file
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Get referecne of particuarl TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Fill form field with arabic text
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

##Conclusion

In this tutorial, we explored how to populate a PDF form field with Arabic text using Aspose.PDF for .NET. We walked through the process step by step and explained the relevant C# source code. By following these instructions, you can easily integrate Arabic text fill functionality into your .NET applications. If you have any further questions or need more information, feel free to contact the Aspose.PDF support team or check out the additional resources below.
