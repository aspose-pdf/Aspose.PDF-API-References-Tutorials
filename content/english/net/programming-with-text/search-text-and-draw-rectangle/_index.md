---
title: Search Text And Draw Rectangle
linktitle: Search Text And Draw Rectangle
second_title: Aspose.PDF for .NET API Reference
description: Learn to search text in PDFs and highlight it with rectangles using Aspose.PDF for .NET! Easy step-by-step tutorial for enhanced PDF manipulation skills.
type: docs
weight: 460
url: /net/programming-with-text/search-text-and-draw-rectangle/
---
## Introduction

Are you looking to enhance your PDF manipulation skills? Do you want to learn how to search for specific text in PDF files and highlight it with a rectangle? You've landed on the perfect guide! Today, I'll walk you through how to use Aspose.PDF for .NET to search for text in a PDF document and draw rectangles around it. This article will provide a step-by-step tutorial designed with clarity and usefulness in mind, ensuring you can follow along and apply these techniques to your projects. 

## Prerequisites

Before diving into the tutorial, let’s prepare what you need to ensure a smooth workflow:

1. Basic Understanding of .NET: You should be familiar with C# programming and the .NET framework to follow this tutorial effectively.
   
2. Visual Studio Installed: You will need an integrated development environment (IDE) to write and test your code. Visual Studio Community is a great option, and it’s free.
   
3. Aspose.PDF for .NET: You need to have the Aspose.PDF library installed in your project. You can download it [here](https://releases.aspose.com/pdf/net/) or consider a [temporary license](https://purchase.aspose.com/temporary-license/) for extended features.
   
4. Sample PDF Document: For this tutorial, you will need a sample PDF file named `SearchAndGetTextFromAll.pdf` stored in your project directory. 

## Import Packages

To get started, you’ll first need to import the necessary packages into your .NET project. Follow these steps:

### Open Visual Studio

Launch Visual Studio and create a new Console Application or use an existing one where you want to implement the PDF functionalities.

### Add Aspose.PDF to Your Project

1. Right-click on your project in the Solution Explorer.
2. Select "Manage NuGet Packages."
3. Search for `Aspose.PDF` and install the latest version.

By doing this, you’re setting the groundwork for all the amazing PDF manipulations you’re about to perform.

## Import Namespaces

At the top of your program file, you’ll want to import the relevant namespaces from the Aspose library:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

This makes it easier to access classes and methods within the Aspose.PDF library for your tasks.


Now that you have everything set up let’s break down the process of searching for text in a PDF and drawing a rectangle around it into manageable steps.

## Step 1: Set the Path for Your Document

First, set the path to your PDF file. Make sure to replace `YOUR DOCUMENT DIRECTORY` with the actual path where your `SearchAndGetTextFromAll.pdf` is stored.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF Document

Next, create an instance of the `Document` class to load your PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

This line of code opens your specified PDF file, allowing you to manipulate it further.

## Step 3: Create a Text Absorber

Now, you’ll need a way to search for text within that document. For this, we use the `TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

The regular expression `@"[\S]+"` is designed to match any non-whitespace string in the PDF. 

## Step 4: Configure Text Search Options

Next, you should set up the text search options:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

Here, the `true` parameter means that the search will be case-sensitive. You can set it to `false` if you want a case-insensitive search.

## Step 5: Accept the Text Absorber in the Document

With your `TextFragmentAbsorber` and search options ready, it’s time to absorb text from the document:

```csharp
document.Pages.Accept(textAbsorber);
```

This method examines each page in your PDF to find text fragments that match the specified pattern.

## Step 6: Create a PdfContentEditor

To draw shapes on the document, you will need the `PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

This editor allows you to manipulate and edit the PDF content easily.

## Step 7: Loop Through Found Text Fragments

Now, you’ll want to loop through the found text fragments to draw rectangles around them:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

This loop iterates over each text fragment and their segments, calling a `DrawBox` method for rectangle drawing.

## Step 8: Define the DrawBox Method

You need to define the `DrawBox` method, which will handle the rectangle drawing logic. Here’s a simple implementation:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Calculate the rectangle dimensions based on the text segment
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Draw a rectangle using the calculated values
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

This method determines the position and size of the rectangle based on the segment’s bounding rectangle and uses the editor to draw it.

## Step 9: Save the Modified Document

After drawing the rectangles around the found text, you can save the modified document:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Make sure your new file is saved with a distinct name to avoid overwriting your original document.

## Step 10: Confirmation Message

Finally, print a confirmation message to the console to let you know that the operation was successful:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

And there you have it! You’ve successfully created a script to search for text in a PDF and highlight it with rectangles.

## Conclusion

Congratulations! You’ve just unlocked a powerful skill that can greatly enhance your PDF manipulation abilities using Aspose.PDF for .NET. With just a few simple steps, you can search for any text in your document and highlight it visually, making your PDF documents more interactive and manageable. Don't hesitate to experiment with different regex patterns and color options to really make this tool your own!

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that provides a comprehensive way to create, manipulate, and convert PDF documents programmatically.

### Can I use Aspose.PDF for free?
Yes, Aspose offers a free trial that you can use to test the library’s functionalities. Check it out [here](https://releases.aspose.com/).

### What programming language do I need to use with Aspose.PDF for .NET?
Aspose.PDF for .NET is designed to be used with C# and other .NET languages.

### How do I get help with Aspose.PDF?
You can visit the Aspose support forum for help regarding any issue or query you might have. Find support [here](https://forum.aspose.com/c/pdf/10).

### Where do I download Aspose.PDF for .NET?
You can download the library from the Aspose website, [here](https://releases.aspose.com/pdf/net/).
