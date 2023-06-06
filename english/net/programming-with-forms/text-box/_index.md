---
title: Text Box
linktitle: Text Box
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a text field in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 290
url: /net/programming-with-forms/text-box/
---

In this guide, we will explain step by step how to use the Aspose.PDF library for .NET to create a text field in a PDF document. We'll show you how to open the document, create the text field, customize its properties, and save the edited PDF.

## Step 1: Configuring the document directory

The first step is to configure the document directory where the PDF file you want to work on is located. You can use the `dataDir` variable to specify the directory path.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to your documents directory.

## Step 2: Opening the PDF document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Make sure that the PDF file is present in the specified documents directory.

## Step 3: Creating the text field

We will create a text field using the `TextBoxField` class. You can specify position coordinates and field size using the `Rectangle` class.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Customize the coordinates, size, partial name and text field value as needed.

## Step 4: Customize text field properties

In this step, we will customize the text field properties such as border, color, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Customize the text field properties according to your preferences.

## Step 5: Adding the field to the document

Now that we have created and configured the text field, we can add it to the PDF document.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Step 6: Saving the modified PDF

Finally, we can save the modified PDF using the `Save` method of the `Document` class.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Be sure to specify the full path and filename for the edited PDF.

### Sample source code for Text Box using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Create a field
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = new Border(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Add field to the document
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Save modified PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this guide, we learned how to use the Aspose.PDF library for .NET to create a text field in a PDF document. By following the described steps, you can customize the properties of the text field and add it to the document as needed. Feel free to further explore the features of Aspose.PDF for .NET to expand the possibilities of manipulating PDF files.
