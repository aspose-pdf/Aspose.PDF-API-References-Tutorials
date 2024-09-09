---
title: Grouped Check Boxes In PDF Document
linktitle: Grouped Check Boxes In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create grouped checkboxes (radio buttons) in a PDF document using Aspose.PDF for .NET with this step-by-step tutorial.
type: docs
weight: 170
url: /net/programming-with-forms/grouped-check-boxes/
---
## Introduction

Creating interactive PDFs isn't as difficult as it might sound, especially when you have powerful tools like Aspose.PDF for .NET at your disposal. One of the interactive elements you might need to add to your PDF documents is grouped checkboxes, or more specifically, radio buttons that allow users to select one option from a set. This tutorial will walk you through the process of adding grouped checkboxes (radio buttons) to a PDF document using Aspose.PDF for .NET. Whether you’re a beginner or a seasoned developer, you’ll find this guide engaging, detailed, and easy to follow.

## Prerequisites

Before we dive into the step-by-step guide, let's cover some essential prerequisites:

1. Aspose.PDF for .NET: Make sure you have the Aspose.PDF library installed. If not, you can [download it here](https://releases.aspose.com/pdf/net/).
2. IDE: You should have a development environment set up, such as Visual Studio.
3. .NET Framework: The project should target a version of the .NET Framework compatible with Aspose.PDF.
4. Basic C# Knowledge: Familiarity with C# and PDF manipulation is required to follow along smoothly.
5. License: Aspose.PDF requires a license for full functionality. You can [obtain a temporary license](https://purchase.aspose.com/temporary-license/) if needed.

## Import Packages

Before starting, ensure you have imported the necessary namespaces into your project:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

These packages will give you access to all the classes and methods required to manipulate PDF documents, including creating radio buttons and defining their properties.

In this section, we'll break down the process of creating grouped checkboxes (radio buttons) into clear, easy-to-follow steps.

## Step 1: Create a New PDF Document

The first step is to create an instance of the `Document` object, which will represent your PDF file. Then, add a blank page to your document where you'll be placing your grouped checkboxes.

```csharp
// Instantiate Document object
Document pdfDocument = new Document();

// Add a page to the PDF file
Page page = pdfDocument.Pages.Add();
```

This sets up the foundation for adding any elements, such as radio buttons, to the PDF.

## Step 2: Initialize Radio Button Field

Next, we need to create a `RadioButtonField` object, which will hold the grouped checkboxes (radio buttons). This field is added to the specific page where the checkboxes will appear.

```csharp
// Instantiate RadioButtonField object and assign it to the first page
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Think of this as the container that will group the individual radio button options together.

## Step 3: Add Radio Button Options

Now, let’s add the individual radio button options to the field. In this example, we’ll add two radio buttons and specify their positions using the `Rectangle` object.

```csharp
// Add first radio button option and specify its position using Rectangle
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Set option names for identification
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

Here, the `Rectangle` object defines the coordinates and size of each radio button on the page.

## Step 4: Customize the Style of Radio Buttons

You can customize the appearance of the radio buttons by setting their `Style` property. For instance, you might want square-shaped checkboxes or cross-shaped ones.

```csharp
// Set the style of the radio buttons
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

This allows you to control the look and feel of the checkboxes, making them more user-friendly and visually appealing.

## Step 5: Configure Border Properties

Borders play a vital role in making the checkboxes easily identifiable. Here, we'll add solid borders around each radio button option and define their width and color.

```csharp
// Configure the border of the first radio button
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Configure the border of the second radio button
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

This step ensures that each radio button has a well-defined border, improving the document's readability.

## Step 6: Add Radio Button Options to the Form

Now, we’ll add the radio buttons to the document's form. This is the final step in grouping the checkboxes together under a single field.

```csharp
// Add radio button field to the form object of the document
pdfDocument.Form.Add(radio);
```

The form object acts as a container for all interactive elements, including our grouped checkboxes.

## Step 7: Save the PDF Document

Finally, once everything is set up, you can save the PDF document to your desired location.

```csharp
// Define the output file path
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Save the PDF document
pdfDocument.Save(dataDir);

// Confirm successful creation
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

And that’s it! You’ve successfully created a PDF with grouped checkboxes using Aspose.PDF for .NET.

## Conclusion

Adding interactive elements like grouped checkboxes to PDF documents can seem tricky at first, but with Aspose.PDF for .NET, it becomes a breeze. By following this step-by-step guide, you've learned how to set up a basic PDF document, add grouped radio buttons, customize their appearance, and save the final result. Whether you're building forms, surveys, or any other type of interactive PDF, this guide gives you a solid foundation to start with.

## FAQ's

### Can I add more than two radio buttons to a group?
Absolutely! Simply instantiate additional `RadioButtonOptionField` objects and add them to the `RadioButtonField` as shown in the tutorial.

### How do I handle multiple groups of checkboxes in one document?
To create multiple groups, instantiate separate `RadioButtonField` objects for each group.

### Is there a limit to the number of checkboxes I can add?
No, Aspose.PDF for .NET does not impose any limits on the number of checkboxes you can add to a PDF.

### Can I change the appearance of checkboxes after they've been added?
Yes, you can modify the properties like border style, width, and color after the checkboxes have been added.

### Is it possible to use images as radio buttons?
Yes, Aspose.PDF allows you to use custom images as radio buttons by setting the `Appearance` property of each radio button option.
