---
title: Set Radio Button Caption
linktitle: Set Radio Button Caption
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set radio button captions in PDFs using Aspose.PDF for .NET. This step-by-step guide walks you through loading, modifying, and saving your PDF forms.
type: docs
weight: 280
url: /net/programming-with-forms/set-radio-button-caption/
---
## Introduction

If you're diving into PDF manipulation with Aspose.PDF for .NET, you're in for a treat! Today, we're focusing on a practical feature: setting radio button captions in your PDF forms. Radio buttons are essential for user forms where you need a choice from a set of options. Imagine them as multiple-choice questions where only one answer is allowed. This tutorial will walk you through the process of updating radio button captions in a PDF form, so your documents are both interactive and user-friendly. 

## Prerequisites

Before diving into the code, there are a few things you'll need to ensure you have:

1. Aspose.PDF for .NET: Make sure you have the Aspose.PDF library installed. This library will help you manipulate PDF files programmatically.
2. Development Environment: You should have a .NET development environment set up, such as Visual Studio.
3. Sample PDF Form: For this tutorial, you’ll need a sample PDF form with radio buttons. You can use any existing PDF form or create a new one with radio buttons.
4. Basic Knowledge of C#: This guide assumes you have a basic understanding of C# and .NET programming concepts.

If you haven’t yet installed Aspose.PDF for .NET or you need a temporary license, you can [download it here](https://releases.aspose.com/pdf/net/) or [get a temporary license](https://purchase.aspose.com/temporary-license/).

## Import Packages

To get started, you need to import the necessary packages in your C# project. Here’s how to include the Aspose.PDF library:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Make sure you have these packages added to your project via NuGet or your preferred method.

## Step 1: Load the PDF Form

First, you need to load the PDF form that contains the radio buttons. The `Aspose.Pdf.Facades.Form` class is used for this purpose. Here’s how you do it:

```csharp
// Define the path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load the source PDF form
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

In this code snippet:
- `dataDir` specifies the path where your PDF is located.
- `Form` class is used to interact with the form fields within the PDF.
- `Document` class provides access to the PDF document’s pages.

## Step 2: Iterate Through Radio Button Fields

Next, you’ll need to iterate through the fields in your form to identify and manipulate the radio button fields:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

In this loop:
- `FieldNames` provides a list of all field names in the PDF.
- `GetButtonOptionValues(item)` retrieves the options available for each radio button.

## Step 3: Modify Radio Button Options

Once you’ve identified the radio button fields, you can modify their options. For this, you need to cast the field to `RadioButtonField` and update its options:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Here:
- We check if the field name contains "radio1" to identify the specific radio button field we want to modify.
- `RadioButtonField` is cast from the form fields to make specific modifications.

## Step 4: Set the Caption for the Radio Button

To set or update the caption for the radio button, you will need to create a `TextFragment` and use `TextBuilder` to place it in the desired location:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // Create TextParagraph object
        TextParagraph par = new TextParagraph();
        // Set paragraph position
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Specify word wraping mode
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Add new TextFragment to paragraph
        par.AppendLine(updatedFragment);
        // Add the TextParagraph using TextBuilder
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

In this part:
- `TextFragment` is used to define the text and its appearance.
- `TextParagraph` helps position and format the text.
- `TextBuilder` adds the text to the specified page of the PDF.

## Step 5: Save the Updated PDF

Finally, save the updated PDF to a new file:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

This will ensure that:
- The changes are applied to the PDF.
- The original radio button option is removed as specified.

## Conclusion

Modifying radio button captions in a PDF form using Aspose.PDF for .NET can greatly enhance the interactivity and usability of your documents. With the steps outlined in this tutorial, you can easily load a PDF, update radio button options, and save your changes. This approach is handy for form management and ensures your PDFs meet the exact needs of your users. Dive into Aspose.PDF and explore its capabilities for other PDF manipulations!

## FAQ's

### Can I update multiple radio button fields at once?
Yes, you can iterate through all radio button fields and apply changes as needed.

### Do I need a license to use Aspose.PDF?
You can start with a free trial, but a license is required for extended use. [Get a license here](https://purchase.aspose.com/buy).

### How can I test the changes before saving the PDF?
You can preview the PDF in your development environment or use a PDF viewer to check the modifications.

### Is Aspose.PDF compatible with all versions of .NET?
Aspose.PDF supports various versions of .NET. Ensure you check compatibility with your specific .NET version.

### Can I manipulate other form fields similarly?
Yes, similar techniques can be applied to other types of form fields in PDF documents.
