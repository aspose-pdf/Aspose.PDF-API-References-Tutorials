---
title: Text In Footer Of PDF File
linktitle: Text In Footer Of PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily add text to the footer of a PDF file using Aspose.PDF for .NET. Step-by-step guide included for seamless integration.
type: docs
weight: 180
url: /net/programming-with-stamps-and-watermarks/text-in-footer/
---
## Introduction

Are you looking to add custom text in the footer of a PDF file using Aspose.PDF for .NET? You're in the right place! Whether you want to include page numbers, dates, or any other custom text, this tutorial will walk you through the entire process. With Aspose.PDF, a robust PDF manipulation library, adding a footer is incredibly easy. In this article, we’ll explore the step-by-step process to add text to the footer of every page in your PDF file. It’s quick, simple, and perfect for those who want to automate PDF customizations in their .NET applications.


## Prerequisites

Before we jump into coding, let’s ensure you have everything ready:

- Aspose.PDF for .NET: Make sure you have Aspose.PDF for .NET installed. If not, you can [download it here](https://releases.aspose.com/pdf/net/).
- IDE: You’ll need a development environment like Visual Studio.
- Basic Knowledge of C#: A basic understanding of C# and .NET is required.
- License: While you can use Aspose.PDF in evaluation mode, for full functionality, consider getting a [free trial](https://releases.aspose.com/) or applying for a [temporary license](https://purchase.aspose.com/temporary-license/).

## Import Packages

Before we begin with the coding part, make sure to import the necessary namespaces. This will ensure the classes and methods from the Aspose.PDF library are available in your project.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Now that you're set, let’s break down the process of adding text to the footer of a PDF file into easy-to-follow steps.

## Step 1: Initialize Your Project and Set Document Directory

Before you can work with your PDF files, you need to specify the path to your documents directory. This is where your PDF file is located and where the modified file will be saved.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Here, replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your folder. This folder will contain the original PDF file and will also serve as the output location for the modified file.

## Step 2: Load the PDF Document

The next step is to load the PDF file into your project. The `Document` class from Aspose.PDF allows you to open and manipulate existing PDF documents.

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Here, `TextinFooter.pdf` is the file we are working with. You can replace this with your own file name.

## Step 3: Create the Footer Text

Now, let’s create the footer text that will be stamped on each page. This is done using the `TextStamp` class. The text you define will be used as the footer for all pages.

```csharp
// Create footer
TextStamp textStamp = new TextStamp("Footer Text");
```

In this case, we’ve created a simple footer text saying "Footer Text". Feel free to customize this with your own message. It could be something like "Confidential" or a page number if you wish.

## Step 4: Set Footer Properties

To position the footer correctly, we need to adjust some properties such as margins, alignment, and positioning. The `TextStamp` class gives you full control over where and how the footer text is displayed.

```csharp
// Set properties of the stamp
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Here, we’ve set the bottom margin to 10 units, aligned the text to the center horizontally, and placed it at the bottom of the page vertically. You can tweak these values depending on your specific layout needs.

## Step 5: Apply Footer to All Pages

Now comes the fun part—applying the footer to every page in the PDF. By iterating over all pages in the document, we can add the footer text to each one.

```csharp
// Add footer on all pages
foreach (Page page in pdfDocument.Pages)
{
    page.AddStamp(textStamp);
}
```

This loop ensures that the footer is stamped on all pages of the document, regardless of how many pages the PDF has.

## Step 6: Save the Updated PDF File

Once the footer has been added to all pages, the final step is to save the modified PDF file to the specified directory.

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
// Save updated PDF file
pdfDocument.Save(dataDir);
```

We’re saving the file with a new name, `TextinFooter_out.pdf`, in the same directory. Feel free to rename it as needed.

## Step 7: Confirm Success

Finally, you can print a success message to the console, letting the user know that the PDF was updated successfully.

```csharp
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);
```

And that's it! You’ve successfully added text to the footer of every page in your PDF.

## Conclusion

Adding a footer to a PDF document using Aspose.PDF for .NET is a simple and powerful way to customize your PDF files. With just a few lines of code, you can add personalized text, such as dates, titles, or page numbers, to every page in the document. By following this guide, you now have the knowledge to implement this functionality in your .NET applications.

## FAQ's

### Can I add different footers to each page in the PDF?  
Yes, you can add unique footers to each page by specifying different `TextStamp` objects for each page.

### How do I change the font style of the footer text?  
You can customize the text by using the `TextStamp.TextState` property to set font, size, and color.

### Can I add images in the footer instead of text?  
Yes, you can use `ImageStamp` to add images to the footer of a PDF file.

### Is it possible to add a footer only to specific pages?  
Absolutely! You can specify the page numbers where you want the footer by targeting specific `Page` objects.

### How can I remove an existing footer from a PDF?  
You can clear existing stamps using the `Page.DeleteStampById` method or by using `RemoveStamp` to remove all stamps.
