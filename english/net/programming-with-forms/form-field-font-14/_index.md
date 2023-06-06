---
title: Form Field Font 14
linktitle: Form Field Font 14
second_title: Aspose.PDF for .NET API Reference
description: Easily configure the font of form fields in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 110
url: /net/programming-with-forms/form-field-font-14/
---

In this tutorial, we will show you how to configure the font of a form field using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

Open the existing PDF document:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Step 3: Get a particular form field

Get the desired form field (in this example, we're using the "textbox1" field):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Step 4: Create a font object

Create a font object for the new font you want to use (for example, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Step 5: Configure font information for the form field

Configure the font information for the form field using the font created earlier:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Step 6: Save the updated document

Save the updated PDF document:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Sample source code for Form Field Font 14 using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Get particular form field from document
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Create font object
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Set the font information for form field
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to configure the font of a form field using Aspose.PDF for .NET. By following these steps, you can easily specify the font and font size for form fields in your PDF documents using Aspose.PDF.
