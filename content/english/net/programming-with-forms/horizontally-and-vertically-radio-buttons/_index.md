---
title: Horizontally And Vertically Radio Buttons
linktitle: Horizontally And Vertically Radio Buttons
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create horizontally and vertically aligned radio buttons in PDF using Aspose.PDF for .NET with this step-by-step tutorial.
type: docs
weight: 180
url: /net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Introduction

Creating interactive PDF forms can significantly enhance user experience, especially when it comes to collecting information. One of the most common form elements is the radio button, which allows users to select one option from a set. In this tutorial, we will explore how to create horizontally and vertically aligned radio buttons using Aspose.PDF for .NET. Whether you're a seasoned developer or just starting, this guide will walk you through the process step-by-step, ensuring you have a clear understanding of each part.

## Prerequisites

Before diving into the code, there are a few prerequisites you should have in place:

1. Aspose.PDF for .NET: Ensure you have the Aspose.PDF library installed. You can download it from the [site](https://releases.aspose.com/pdf/net/).
2. Visual Studio: A development environment where you can write and test your code.
3. Basic Knowledge of C#: Familiarity with C# programming will help you understand the code snippets better.

## Import Packages

To get started, you need to import the necessary packages in your C# project. Here’s how you can do it:

### Create a New Project

Open Visual Studio and create a new C# project. You can choose a Console Application for simplicity.

### Add Aspose.PDF Reference

1. Right-click on your project in the Solution Explorer.
2. Select "Manage NuGet Packages."
3. Search for "Aspose.PDF" and install the latest version.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Now that you have everything set up, let’s break down the code to create horizontally and vertically aligned radio buttons.

## Step 1: Set Up the Document Directory

In this step, we will define the path to the directory where your PDF documents will be stored.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where you want to save your PDF file. This is crucial as it tells the program where to look for input files and where to save the output.

## Step 2: Load the Existing PDF Document

Next, we need to load the PDF document that we will be working with. This is done using the `FormEditor` class.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Here, we create an instance of `FormEditor` and bind it to an existing PDF file named `input.pdf`. Make sure this file exists in your specified directory.

## Step 3: Configure Radio Button Properties

Now, let’s set some properties for our radio buttons. This includes the gap between the buttons, their orientation, and their size.

```csharp
formEditor.RadioGap = 4; // Distance between radio button options
formEditor.RadioHoriz = true; // Set to true for horizontal alignment
formEditor.RadioButtonItemSize = 20; // Size of the radio button
formEditor.Facade.BorderWidth = 1; // Border width
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Border color
```

These properties will help define how the radio buttons will appear in the PDF. The `RadioGap` property controls the space between the buttons, while `RadioHoriz` determines their layout.

## Step 4: Add Horizontal Radio Buttons

Now, let’s add the horizontal radio buttons to the PDF.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

In this code, we define the items for the radio buttons and add them to the PDF. The `AddField` method takes several parameters, including the field type, field name, and coordinates for placement.

## Step 5: Add Vertical Radio Buttons

Next, we will add the vertical radio buttons. To do this, we need to change the orientation back to vertical.

```csharp
formEditor.RadioHoriz = false; // Set to false for vertical alignment
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Just like before, we define the items and add them to the PDF, but this time they will be aligned vertically.

## Step 6: Save the PDF Document

Finally, we need to save the modified PDF document.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

This code saves the PDF with the newly added radio buttons. Make sure to check the specified directory for the output file.

## Conclusion

Creating radio buttons in a PDF using Aspose.PDF for .NET is a straightforward process. By following the steps outlined in this tutorial, you can easily add both horizontally and vertically aligned radio buttons to your PDF forms. This not only enhances the interactivity of your documents but also improves the overall user experience. So, go ahead and give it a try!

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and convert PDF documents programmatically.

### Can I use Aspose.PDF for free?
Yes, Aspose offers a free trial version that you can use to evaluate the library. You can download it [here](https://releases.aspose.com/).

### How do I get support for Aspose.PDF?
You can get support by visiting the [Aspose forum](https://forum.aspose.com/c/pdf/10).

### Is it possible to create other form elements with Aspose.PDF?
Absolutely! Aspose.PDF supports various form elements, including text fields, checkboxes, and dropdowns.

### Where can I purchase Aspose.PDF for .NET?
You can buy Aspose.PDF for .NET from the [purchase page](https://purchase.aspose.com/buy).
