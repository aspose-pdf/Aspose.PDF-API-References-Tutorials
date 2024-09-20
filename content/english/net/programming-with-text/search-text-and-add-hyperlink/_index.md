---
title: Search Text And Add Hyperlink
linktitle: Search Text And Add Hyperlink
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search text and add hyperlinks in PDFs using Aspose.PDF for .NET with our step-by-step tutorial.
type: docs
weight: 450
url: /net/programming-with-text/search-text-and-add-hyperlink/
---
## Introduction

Are you looking for a way to not just manipulate PDFs but also enhance them by inserting hyperlinks? Well, you're in the right spot! With the powerful Aspose.PDF for .NET library, you can search for text patterns in your PDF documents and seamlessly add hyperlinks. Imagine having a document that not only conveys information but also connects readers to relevant resources just by clicking on a link. Sounds neat, right? In this tutorial, we’ll guide you step-by-step on how to search for text using regular expressions and add hyperlinks within your PDFs. Whether you’re a seasoned developer or just starting, you’ll find this process simple and rewarding.

## Prerequisites

Before we dive into the nitty-gritty, let’s make sure you have everything you need to follow along. Here’s a handy checklist:

- .NET Framework: You should have the .NET framework installed on your machine (version 4.0 or higher).
- Aspose.PDF for .NET Library: Don’t forget to download and add a reference to the Aspose.PDF library in your project. You can find it [here](https://releases.aspose.com/pdf/net/).
- IDE: You’ll need an Integrated Development Environment (IDE) like Visual Studio to write and run the code.
- Sample PDF File: Grab a sample PDF file on which you can test the code. You can create a simple PDF or use one of your existing documents.

Once you’ve ticked off everything on this list, we’re ready to roll!

## Import Packages

The first step in our journey is to import the necessary packages. This is where we tell our project what tools we’ll be using. Here’s how you can do it:

In your C# file, start by including the following namespaces at the top:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

By importing these namespaces, you give your program access to all the cool features Aspose.PDF has to offer.

Now that we’re all set up, it’s time to get into action. We’ll go through this in a series of steps, so follow along closely!

### Step 1: Set Your Document Directory

First, you’ll need to specify where your PDF files are stored. Modify the `dataDir` variable to point to your document's directory. Here’s how you do it:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents.

### Step 2: Create a TextFragmentAbsorber

Next, we need a tool to find the text we want to link. Enter the `TextFragmentAbsorber`. This little guy will help us search for the specific text pattern in our PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Here, we’re looking for a specific pattern: four digits, a dash, followed by another four digits (like a phone number or year).

### Step 3: Enable Regular Expression Search

We’re already using a regular expression to find our text pattern, but we need to make sure our `absorber` knows it’s enabled. This is crucial for it to search properly.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Step 4: Initialize PdfContentEditor

Now that we have our absorber ready, we need a `PdfContentEditor` to work with our PDF file. This class lets us bind to our PDF and manipulate it.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Step 5: Bind Your Source PDF File

With our content editor ready, it’s time to bind it to the actual PDF file we want to work on.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

Make sure to replace `"SearchRegularExpressionPage.pdf"` with the name of your PDF file.

### Step 6: Accept the Absorber for the Page

We need to let our editor know that we want to search on a specific page of the document. In this case, let’s go with Page 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Step 7: Prepare to Loop Through Text Fragments

Now, we’re ready to loop through all the text fragments found by our absorber. We’ll tweak their appearance and set up our hyperlink.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Here, we’re setting some parameters, like the color of our hyperlink.

### Step 8: Loop Through Each Text Fragment

For every text fragment that matches our search, we’re going to change its color and create a hyperlink. Here’s what that looks like:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, blue, actionName);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Step 9: Save the Edited PDF

We’re almost done! Now it’s time to save our changes to a new PDF file.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Step 10: Close the Editor

Finally, don’t forget to close your document to release resources!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Now, you’ve just created a PDF with a hyperlink that was dynamically generated based on the search results. How cool is that?

## Conclusion

And there you have it! By following these steps, you’ve learned how to search through a PDF and add hyperlinks using the Aspose.PDF for .NET library. This can open up a world of possibilities, especially if you’re working with documents that require interactivity. Imagine adding links to related resources, reference websites, or even internal pages—all with just a few lines of code!
## FAQ's

### What is Aspose.PDF for .NET?  
Aspose.PDF for .NET is a library that allows developers to create, manipulate, and manage PDF documents in .NET applications.

### How can I download Aspose.PDF for .NET?  
You can download the library [here](https://releases.aspose.com/pdf/net/).

### Can I try Aspose.PDF for free?  
Absolutely! You can get a free trial [here](https://releases.aspose.com/).

### Is there support available for Aspose products?  
Yes, you can find support and community discussions [here](https://forum.aspose.com/c/pdf/10).

### How can I obtain a temporary license for Aspose.PDF?  
You can request a temporary license [here](https://purchase.aspose.com/temporary-license/).
