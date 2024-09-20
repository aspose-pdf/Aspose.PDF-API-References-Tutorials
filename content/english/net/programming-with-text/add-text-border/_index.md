---
title: Add Text Border In PDF File
linktitle: Add Text Border In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a text border in a PDF file using Aspose.PDF for .NET with this step-by-step guide. Enhance your PDF documents.
type: docs
weight: 70
url: /net/programming-with-text/add-text-border/
---
## Introduction

Creating and manipulating PDF documents has become an essential skill in today’s digital world. Whether you're generating reports, invoices, or any other type of documentation, having control over how your text appears can make a significant difference. One such enhancement you might want to implement is adding a border around your text in a PDF file. In this guide, we will walk you through the steps to add a text border in a PDF file using the Aspose.PDF library for .NET. So, let’s dive right in!

## Prerequisites

Before we start, there are a few things you need to have in place. Don't worry, it's pretty straightforward!

1. Visual Studio: Make sure you have Visual Studio installed on your machine. This will be your development environment where you will write and run your code.
2. Aspose.PDF for .NET: You’ll need to download and install the Aspose.PDF library. You can get it from the [Aspose PDF for .NET download page](https://releases.aspose.com/pdf/net/). If you want to try it out first, you can also get a [free trial here](https://releases.aspose.com/).
3. Basic Knowledge of C#: A fundamental understanding of C# programming language will help you follow along with the examples easily.
4. .NET Framework: Ensure that you have the .NET Framework installed and set up in your project.

Once you have these prerequisites in place, you’re ready to start coding!

## Import Packages

Now that we have everything set up, let’s import the necessary packages to use Aspose.PDF in our project. You can do this by adding the following using directives at the top of your C# file:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

These namespaces will allow you to work with PDF documents and text fragments effectively. 

Now, let’s break down the process of adding a text border into detailed steps. We’ll go through each step so you can understand exactly what’s happening under the hood.

## Step 1: Set Up the Document

First things first, we need to create a new PDF document. This is where all our magic will happen.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create new document object 
Document pdfDocument = new Document();
```

In this step, we specify the directory where we want to save our PDF file. Then we create a new instance of the `Document` class, which represents our PDF document.

## Step 2: Add a New Page

Next, we need to add a page to our document. Think of this as adding a blank canvas where we’ll place our text.

```csharp
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

Here, we call the `Add()` method on the `Pages` collection of our `pdfDocument` object. This adds a new page to the document, and we store a reference to it in the `pdfPage` variable.

## Step 3: Create a Text Fragment

Now, let’s create the text that we want to display in our PDF. This is where we define the content of our text fragment.

```csharp
// Create text fragment
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

In this code, we create a new `TextFragment` object with the text "main text". We also set its position on the page using the `Position` class. The coordinates (100, 600) specify where the text will be placed on the page.

## Step 4: Set Text Properties

Next, we’ll customize our text fragment to make it visually appealing. This includes setting the font size, font type, background color, and foreground color.

```csharp
// Set text properties
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

Here, we set the font size to 12, use "Times New Roman" as the font, and apply a light gray background color with red text. These properties help enhance the visibility of the text.

## Step 5: Set the Stroking Color for the Border

Now, we’re getting to the exciting part—adding a border around our text!

```csharp
// Set StrokingColor property for drawing border (stroking) around text rectangle
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

In this step, we specify the color of the border we want to draw around our text. Here, we’ve chosen a dark red color.

## Step 6: Enable the Text Rectangle Border

To actually draw the border around our text, we need to enable the `DrawTextRectangleBorder` property.

```csharp
// Set DrawTextRectangleBorder property value to true
textFragment.TextState.DrawTextRectangleBorder = true;
```

By setting this property to `true`, we tell Aspose.PDF to draw the border around the text rectangle based on the specified stroking color.

## Step 7: Append the Text Fragment to the Page

Now that we have our text fragment ready with all the properties set, it’s time to add it to the page.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

Here, we create a `TextBuilder` object that is associated with our `pdfPage`. We then use the `AppendText` method to add our `textFragment` to the page. 

## Step 8: Save the Document

Finally, we need to save our PDF document to the specified directory. This is the moment of truth!

```csharp
// Save the document
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

In this step, we call the `Save` method on our `pdfDocument` object, providing the path where we want to save the file. Once you run the code, you should find your newly created PDF with the text border in the specified directory!

## Conclusion

And there you have it! You’ve successfully added a text border to a PDF file using Aspose.PDF for .NET. This simple yet powerful feature can significantly enhance the readability and aesthetics of your PDF documents. Whether you’re creating reports, brochures, or any other type of documentation, knowing how to manipulate text formatting can come in handy.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and process PDF documents programmatically using the .NET framework.

### Can I try Aspose.PDF for free?
Yes! Aspose offers a [free trial](https://releases.aspose.com/) of their PDF library, allowing you to test its features before making a purchase.

### How do I purchase Aspose.PDF for .NET?
You can buy Aspose.PDF for .NET directly from their [purchase page](https://purchase.aspose.com/buy).

### Is there support available for Aspose.PDF?
Absolutely! You can get support by visiting the [Aspose support forum](https://forum.aspose.com/c/pdf/10).

### What if I need a temporary license?
Aspose provides a [temporary license](https://purchase.aspose.com/temporary-license/) option for developers who need to evaluate the library for a limited time.
