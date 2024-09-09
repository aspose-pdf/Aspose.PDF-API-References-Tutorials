---
title: Radio Button With Options
linktitle: Radio Button With Options
second_title: Aspose.PDF for .NET API Reference
description: Unlock the potential of interactive PDFs by adding radio buttons using Aspose.PDF for .NET. Create engaging forms with ease and improve user experience.
type: docs
weight: 230
url: /net/programming-with-forms/radio-button-with-options/
---
## Introduction

Creating interactive PDF documents can significantly enhance user engagement and streamline data collection. Among the various elements you can incorporate, radio buttons stand out as a user-friendly method of presenting multiple choice options. Using Aspose.PDF for .NET, you can effortlessly add radio buttons into your PDF forms, making it easy for users to select their preferences. Whether you’re working on surveys, feedback forms, or applications, this guide will help you leverage the power of Aspose.PDF to implement radio buttons effectively.

## Prerequisites

Before we get started, there are a few things you'll need to set up to ensure a smooth journey as we create our PDF with radio buttons:

1. Aspose.PDF for .NET: Make sure you have the Aspose.PDF library installed in your project. If you don't have it yet, you can easily download it from the [release page](https://releases.aspose.com/pdf/net/).
2. .NET Framework: A basic understanding of the .NET framework will help you navigate any issues you encounter along the way.
3. Development Environment: You'll need a suitable IDE for .NET (like Visual Studio) where you can write and test your code.
4. Familiarity with C#: While you don’t need to be a pro, having a grasp of C# programming will definitely make this process easier and more enjoyable.
5. Basic Knowledge of PDF Structure: Understanding how PDFs are structured can help when troubleshooting or customizing your forms further.

Once you have all this sorted, you're ready to unleash your creativity into the world of PDFs!

## Import Packages

To get started with radio buttons in Aspose.PDF, you’ll first need to import the essential packages into your C# project. Here’s how you do it:

### Open Your Code Editor

Open your development environment (like Visual Studio) and create a new C# project if you haven’t done it already. 

### Add the Aspose.PDF Reference

Right-click on your project in the Solution Explorer, select Add > Reference, and in the Assemblies section, look for Aspose.PDF. If you’ve installed the library correctly, it should appear in the list. Just check it off and click OK.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Now, your project is ready to leverage the power of Aspose!

With everything set up, let’s create a PDF document filled with radio buttons step by step!

## Step 1: Set Up the Document

First, let's create a new PDF document and add a page to it. This will be the canvas where we paint our radio button options.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
```

In this snippet, we’re establishing a new `Document` object and adding a `Page` to it for our content. Make sure to replace `YOUR DOCUMENT DIRECTORY` with the path where you want to save your PDF.

## Step 2: Create a Table for Layout

Next, we need a layout for our radio buttons. Using a table makes it easier to position them nicely.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "120 120 120"; // Define the column widths
page.Paragraphs.Add(table);
```

Here, we created a `Table` object and specified the widths for our three columns. This creates a tidy layout for our options.

## Step 3: Add Rows to the Table

We’ll now add a row to our table and cells that will contain the radio buttons.

```csharp
Row r1 = table.Rows.Add();
Cell c1 = r1.Cells.Add();
Cell c2 = r1.Cells.Add();
Cell c3 = r1.Cells.Add();
```

We create a new row and three cells in the row. Each cell will house a radio button option.

## Step 4: Add a Radio Button Field

This is where the fun begins – let’s add the radio button field to our PDF!

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf.PartialName = "radio";
doc.Form.Add(rf, 1);
```

We instantiate a `RadioButtonField`, set its name, and then add it to the document form. This field will let the users make their selection.

## Step 5: Configure Radio Button Options

Time to create the options for the radio buttons! We’ll add three options that users can choose from.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
```

Here, we create three `RadioButtonOptionField` instances for each of our choices and assign them names. Getting creative with these names can help better guide users on what to pick.

## Step 6: Set Dimensions for Options

Next, let’s set the size of the radio button options to make them visually appealing.

```csharp
opt1.Width = 15;
opt1.Height = 15;
opt2.Width = 15;
opt2.Height = 15;
opt3.Width = 15;
opt3.Height = 15;
```

With this code, we're defining each radio button's dimensions. You can adjust these values if you want larger or smaller options.

## Step 7: Add Options to the Radio Button Field

Now that the options are created, we need to add them to the radio button field.

```csharp
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

This code not only adds the options but also links them to our radio button field, giving users the ability to select one of the options.

## Step 8: Style the Options

To make our options stand out, let’s style them. We can add borders and set colors.

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");
```

Repeat this styling for `opt2` and `opt3`, adjusting the captions accordingly. This ensures that each option looks professional and engaging.

## Step 9: Add Options to Cells

Next, we need to place these radio buttons into the corresponding cells of our table.

```csharp
c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

This line adds the styled options to the cells we created earlier, neatly organizing them in our table.

## Step 10: Save the PDF Document

Finally, it’s time to save your work! This step commits everything we’ve done into a PDF file.

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
// Save the PDF file
doc.Save(dataDir);
Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
```

With this code, your document will be saved in the specified directory. You can now open this PDF file to see your radio buttons in action. Congratulations on implementing your first interactive PDF!

## Conclusion

Mastering how to create interactive elements like radio buttons with Aspose.PDF for .NET opens up a whole new realm of possibilities for your PDF documents. By following this guide, you should now be equipped to incorporate radio buttons into your projects effortlessly, enhancing user experience and data collection processes. Whether it’s for a simple survey or a complex form, the power to create tailored interactive PDFs is at your fingertips.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that enables developers to create and manipulate PDF documents programmatically.

### How do I install Aspose.PDF for .NET?
You can download the library from the [Aspose release page](https://releases.aspose.com/pdf/net/) and add it to your project.

### Can I create radio buttons in PDFs using other programming languages?
Yes, Aspose.PDF is also available for Java and other languages for similar functionalities.

### Is there a free trial for Aspose.PDF?
Yes, you can explore the functionalities of Aspose.PDF by downloading a [free trial version](https://releases.aspose.com/).

### Where can I get support for Aspose.PDF?
For support, you can visit the [Aspose support forum](https://forum.aspose.com/c/pdf/10) for assistance from experts and community members.
