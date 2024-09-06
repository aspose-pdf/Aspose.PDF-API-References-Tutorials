---
title: Strike Out Words
linktitle: Strike Out Words
second_title: Aspose.PDF for .NET API Reference
description: Learn how to strike out words in a PDF using Aspose.PDF for .NET with this comprehensive step-by-step guide. Enhance your document editing skills.
type: docs
weight: 150
url: /net/annotations/strikeoutwords/
---
## Introduction

Have you ever found yourself needing to emphasize specific text in a PDF by striking it out? Whether you’re reviewing documents, marking up text, or simply need to highlight certain sections, striking out words can be a valuable tool. In this tutorial, we'll explore how to do just that using Aspose.PDF for .NET. This comprehensive guide will walk you through each step, ensuring you have all the information needed to effectively implement this feature in your .NET applications. 

## Prerequisites

Before we jump into the code, there are a few prerequisites you'll need to meet to follow along with this tutorial:

1. Aspose.PDF for .NET Library: Make sure you have the Aspose.PDF for .NET library installed. You can [download it here](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Ensure that you have .NET Framework installed on your machine. This tutorial is designed for .NET applications.

3. Development Environment: You’ll need an IDE like Visual Studio to write and run your code.

4. PDF Document: Have a sample PDF file ready that you want to work with. This will be the document where we'll strike out the text.

5. Basic C# Knowledge: Familiarity with C# programming is necessary to understand and implement the steps in this tutorial.

## Import Packages

Before we can start coding, we need to import the necessary namespaces in our .NET project. This will give us access to the classes and methods required to manipulate PDF files using Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

These namespaces are essential for working with PDF documents, handling text, and adding annotations like strikeouts.

In this section, we'll break down the process of striking out words in a PDF document into simple, manageable steps. Each step will be accompanied by a detailed explanation to ensure you understand how everything works.

## Step 1: Load the PDF Document

The first step is to load the PDF document that you want to edit. This document will be the one where you'll be striking out specific words or phrases.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir`: This variable holds the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where your PDF file is located.
- `Document`: The `Document` class represents a PDF document. By passing the file path to its constructor, we open the PDF file for processing.

## Step 2: Create a TextFragment Absorber to Find Specific Text

Next, we'll create an instance of `TextFragmentAbsorber` to search for a specific text fragment in the PDF document. This allows us to locate the text we want to strike out.

```csharp
// Create TextFragment Absorber instance to search for a specific text fragment
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`: This class is used to find and work with specific text fragments within the PDF document. In this example, we're searching for the word "Estoque". Replace "Estoque" with the word or phrase you want to find in your document.

## Step 3: Iterate Through the Pages of the PDF Document

Now that we have our `TextFragmentAbsorber`, we need to iterate through each page of the PDF document to find the specified text.

```csharp
// Iterate through the pages of the PDF document
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Get the current page of the PDF document
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: This loop iterates through each page of the PDF document.
- `document.Pages[i]`: Retrieves the current page being processed.
- `page.Accept(textFragmentAbsorber)`: This method applies the `TextFragmentAbsorber` to the current page, searching for the specified text.

## Step 4: Collect and Process the Text Fragments

After iterating through the pages, we'll collect the text fragments found and prepare them for further processing.

```csharp
// Create a collection of absorbed text fragments
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`: This collection stores all the text fragments that were found in the document. We'll use this collection in the next step to strike out the text.

## Step 5: Iterate Through the Text Fragments and Strike Them Out

In this step, we'll loop through each text fragment in our collection and apply a strikeout annotation to it.

```csharp
// Iterate over the collection of text fragments
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Get the rectangular dimensions of the TextFragment object
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Instantiate StrikeOut Annotation instance
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Set properties of the strikeout annotation
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Add the annotation to the annotations collection of the text fragment's page
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: This line retrieves the current text fragment.
- `Aspose.Pdf.Rectangle`: We calculate the rectangular dimensions of the text fragment to determine where to apply the strikeout.
- `StrikeOutAnnotation`: This class represents the strikeout annotation. We instantiate it with the calculated rectangle and the current page.
- `strikeOut.Opacity`: This property sets the opacity of the strikeout, making it 80% visible.
- `strikeOut.Color`: We set the color of the strikeout to red. You can change this to any color you prefer.
- `textFragment.Page.Annotations.Add(strikeOut)`: This adds the strikeout annotation to the page.

## Step 6: Save the Modified PDF Document

The final step is to save the modified PDF document with the strikeouts applied.

```csharp
// Save the updated PDF document
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: This creates a new file name for the modified document. The original file remains unchanged.
- `document.Save(dataDir)`: Saves the PDF document with the strikeouts to the specified location.

## Conclusion

Congratulations! You've successfully struck out specific words in a PDF document using Aspose.PDF for .NET. By following this step-by-step guide, you can now customize PDF documents by highlighting or striking out text, making them more dynamic and tailored to your needs. Whether you're annotating legal documents, preparing reports, or just marking up text for review, this tutorial has equipped you with the skills to do so efficiently.

## FAQ's

### Can I change the color of the strikeout?

Yes, you can change the color by modifying the `strikeOut.Color` property. For example, you can set it to `Aspose.Pdf.Color.Blue` for a blue strikeout.

### Is it possible to strike out multiple words at once?

Absolutely! The `TextFragmentAbsorber` can be used to search for any word or phrase in the document. You can apply the strikeout to multiple instances by iterating through the `TextFragmentCollection`.

### What if I want to strike out text on specific pages only?

You can modify the loop that iterates through the pages to include only the pages you want to modify. For example, `for (int i = 1; i <= 3; i++)` would apply the strikeout only to the first three pages.

### How can I adjust the thickness of the strikeout line?

You can adjust the thickness of the strikeout line by modifying the `Border` property of the `StrikeOutAnnotation`. This allows for customization of the strikeout appearance.

### Is there a way to undo the strikeout after saving the document?

Once the document is saved, the strikeout is permanent. If you need to retain the original text without the strikeout, consider saving a backup of the original document before applying any modifications.
