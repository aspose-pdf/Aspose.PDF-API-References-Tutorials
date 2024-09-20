---
title: Specify Line Spacing In PDF File
linktitle: Specify Line Spacing In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to specify line spacing in a PDF using Aspose.PDF for .NET with this step-by-step guide. Perfect for developers seeking precise text formatting.
type: docs
weight: 510
url: /net/programming-with-text/specify-line-spacing/
---
## Introduction

Have you ever struggled with controlling the line spacing in a PDF file? Maybe you’ve had text that looks too crammed together or just doesn't look as polished as you’d like. In this tutorial, we’re going to walk through how you can easily specify line spacing in a PDF using Aspose.PDF for .NET. We’ll be using a simple, step-by-step guide to take you from a blank PDF to one that includes custom line spacing. This is perfect if you need precision in your text layout for documents like reports, invoices, or certificates.

## Prerequisites

Before we jump into the code, let’s make sure you’ve got everything you need:

1. Aspose.PDF for .NET installed. If you don’t have it, grab it from the [Aspose.PDF download page](https://releases.aspose.com/pdf/net/).
2. A .NET development environment (like Visual Studio).
3. A TrueType font file (`.ttf`) that we’ll use in the example. You can use any font, but for this guide, we’ll use the `HPSimplified.TTF` font.
4. Basic knowledge of C# and PDF manipulation.

If you’re ready, let’s move on to importing the necessary packages.

## Import Packages

In your C# project, you’ll need to import the Aspose.PDF namespaces to work with the PDF functionalities. Here’s how you do that:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

These namespaces allow you to create and manipulate PDF documents, as well as work with text formatting and font options.

We’ll break this down into bite-sized steps, so you can follow along easily. Each step will focus on a key part of the process, from setting up your PDF to specifying line spacing.

## Step 1: Set Up Your Project and Define the Document Directory

The first thing we need to do is define where our files are located. This helps the program know where to find the font and where to save the resulting PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

In this step, you’ll replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to where you store your files. This will be where you place your font file (`HPSimplified.TTF`) and where the PDF will be saved.

## Step 2: Load a PDF Document

Now, we need to create a new PDF document. For this guide, we’ll start with a blank document, but you can also load an existing PDF if needed.

```csharp
Document doc = new Document();
```

This creates a new, empty PDF document. Easy, right?

## Step 3: Set Text Formatting Options

Here’s where the magic happens. We’ll specify the line spacing mode for the text we want to add to the PDF. Aspose.PDF gives us several options, but in this guide, we’ll use `LineSpacingMode.FullSize`, which ensures that the line spacing is fully respected.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

This code sets the line spacing mode to `FullSize`, ensuring that text will be displayed with proper spacing. There are other options like `Proportional` if you want different spacing behaviors, but for now, let’s stick with `FullSize`.

## Step 4: Create a Text Fragment

Now, we’re going to create the actual text that will be placed in the PDF. This text will respect the line spacing we’ve defined.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

We’ve created a text fragment with the string `"Hello world"`. You can, of course, customize this text to whatever you like.

## Step 5: Load and Apply a Custom Font

To make the text stand out, we’re going to load a custom TrueType font from a file. This step is optional, but it can add a professional touch to your PDFs.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Here, we load the font file and apply it to the text fragment. If the file path is valid, the font is used. Otherwise, the default font is applied.

## Step 6: Set Text Position and Formatting

Next, we need to position the text on the PDF. We’ll also apply the formatting options we created earlier.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

The `Position` method sets the coordinates where the text will appear on the page (in this case, 100 units from the left and 600 units from the bottom). The formatting options, including the line spacing mode, are applied here.

## Step 7: Add Text to the PDF Page

Now that our text is formatted and positioned, it’s time to add it to the PDF document.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

This code creates a new page in the PDF document and adds the text fragment to it.

## Step 8: Save the PDF

We’ve reached the final step! Now that everything is set up, let’s save the PDF.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

This saves the PDF with the specified line spacing, and your file is ready!

## Conclusion

And that’s it! You’ve just created a PDF document with custom line spacing using Aspose.PDF for .NET. It’s a powerful tool that allows you to control every aspect of your PDF files, and this is just one example of what you can achieve. From text placement to formatting, the possibilities are endless.

If you’re looking to dive deeper into PDF manipulation, Aspose.PDF offers a wealth of features to explore. Don’t hesitate to experiment and push the limits of what you can do with your documents!

## FAQ's

### Can I adjust the line spacing to other modes?  
Yes, you can use other modes like `Proportional` or `Fixed` depending on your needs.

### Is it possible to load fonts from the system instead of a file?  
Yes, you can load system-installed fonts using the `FontRepository`.

### Can I use Aspose.PDF for .NET with other file formats?  
Absolutely! Aspose.PDF for .NET supports a variety of formats like XML, HTML, and more.

### Do I need a license to use Aspose.PDF for .NET?  
Yes, for full functionality, you’ll need a license, which you can obtain [here](https://purchase.aspose.com/buy).

### How do I set the line spacing for multiple paragraphs?  
You can apply `TextFormattingOptions` to each `TextFragment` or `TextParagraph` to control the spacing for multiple lines or paragraphs.
