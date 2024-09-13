---
title: Change Orientation
linktitle: Change Orientation
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to change page orientation of a PDF with Aspose.PDF for .NET. Easy to follow and implement in your projects.
type: docs
weight: 10
url: /net/programming-with-pdf-pages/change-orientation/
---
## Introduction

Have you ever found yourself struggling with a PDF file where the page orientation is just... off? Maybe you’re dealing with a document that was scanned or created incorrectly, and the pages need rotating to make sense. Lucky for us, Aspose.PDF for .NET provides an easy, powerful way to manipulate PDF files in just about any way imaginable—including changing the orientation of your pages. Whether you want to switch from portrait to landscape or vice versa, this guide will walk you through the process step-by-step.

So, if you're ready to dive in and rotate those PDF pages with ease, let’s get started!

## Prerequisites

Before we get into the details of changing page orientation in your PDF, let’s quickly cover what you’ll need to have in place:

- Aspose.PDF for .NET: Make sure you’ve installed the Aspose.PDF library for .NET. If you haven’t, you can [download it here](https://releases.aspose.com/pdf/net/).
- A .NET Development Environment: You can use Visual Studio, JetBrains Rider, or any preferred IDE for working with .NET.
- Basic Knowledge of C#: While this guide is straightforward, some basic understanding of C# will make it even easier to follow.
- A PDF File: The example below assumes you have a PDF file with multiple pages. If you don’t have one handy, create or download a sample PDF to work with.

Also, if you’re just getting started, you can try Aspose.PDF with a [free temporary license](https://purchase.aspose.com/temporary-license/) before deciding to [buy the full version](https://purchase.aspose.com/buy).

## Import Namespaces

Before you can manipulate the orientation of pages in your PDF, you’ll need to import the necessary namespaces in your C# project. Make sure you have the following:

```csharp
using System.IO;
using Aspose.Pdf;
```

With this imported, let’s jump into the main part of the tutorial.

## Step 1: Load the PDF Document

The first thing we need to do is load the PDF file you wish to modify. You can use the `Document` class from the Aspose.PDF namespace to open your PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

This line loads the PDF from your specified directory. Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your file. The `"input.pdf"` is the PDF you want to change the orientation of.

## Step 2: Loop Through Each Page

Now that we have the document loaded, let’s loop through each page in the PDF. We’ll use a `foreach` loop to go through every page, allowing us to apply the orientation change to all of them.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipulate each page
}
```

This loop will iterate through all the pages within the document.

## Step 3: Get the Page’s MediaBox

Every page in a PDF has a `MediaBox` that defines the boundaries of the page. We need to access this to determine the current orientation and modify it.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

The `MediaBox` gives us the dimensions of the page, such as its width, height, and positioning.

## Step 4: Swap the Width and Height

To change the page orientation from portrait to landscape or landscape to portrait, we simply swap the width and height values. This step will adjust the dimensions of the page.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

This code swaps the height and width and repositions the lower-left corner (`LLY`) so that the content fits neatly after rotation.

## Step 5: Update the MediaBox and CropBox

Now that we have the new height and width, let’s apply the changes to the page’s `MediaBox` and `CropBox`. The `CropBox` is essential if the original document had one set, ensuring the entire page displays correctly.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

This step resizes the page based on the new dimensions we just calculated.

## Step 6: Rotate the Page

Finally, we set the rotation angle of the page. Aspose.PDF makes this super simple. We can rotate the page 90 degrees to shift from portrait to landscape or the other way around.

```csharp
page.Rotate = Rotation.on90;
```

This code rotates the page by 90 degrees, flipping it into the desired orientation.

## Step 7: Save the Output PDF

After applying the orientation changes to all the pages, we save the modified document to a new file. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Make sure you provide a new file name (in this case, `ChangeOrientation_out.pdf`) to save the output. This way, you don’t overwrite your original file.

### Conclusion

And there you have it! Changing the page orientation of a PDF file using Aspose.PDF for .NET is as simple as loading the document, looping through the pages, adjusting the MediaBox, and saving the updated file. Whether you’re dealing with a poorly scanned document or need to rotate pages to match your formatting needs, this step-by-step guide should have you covered.

## FAQ's

### Can I rotate specific pages instead of all pages in the PDF?  
Yes, you can modify the loop to target specific pages using their index instead of looping through all pages.

### What is the `MediaBox`?  
The `MediaBox` defines the size and shape of the page in a PDF file. It’s where the content of the page is placed.

### Does Aspose.PDF for .NET work with other file formats?  
Yes, Aspose.PDF can handle a variety of file formats like HTML, XML, XPS, and more.

### Is there a free version of Aspose.PDF for .NET?  
Yes, you can get started with a [free trial](https://releases.aspose.com/) or request a [temporary license](https://purchase.aspose.com/temporary-license/).

### Can I undo the changes once saved?  
Once you save the document, the changes are permanent. Be sure to work on a copy or keep a backup of the original file.
