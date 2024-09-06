---
title: Remove Hyperlinks After Converting From Html
linktitle: Remove Hyperlinks After Converting From Html
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove hyperlinks from HTML documents after converting to PDF using Aspose.PDF for .NET in this step-by-step guide.
type: docs
weight: 250
url: /net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Introduction

In the digital age, converting HTML documents to PDF is a common task. However, sometimes you may want to remove hyperlinks from the converted PDF for various reasons, such as enhancing readability or preventing unwanted navigation. In this tutorial, we will explore how to achieve this using Aspose.PDF for .NET. 

## Prerequisites

Before diving into the code, ensure you have the following prerequisites:

1. Visual Studio: Make sure you have Visual Studio installed on your machine. This will be your development environment.
2. Aspose.PDF for .NET: You need to have the Aspose.PDF library. You can download it from [here](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: Familiarity with C# programming will help you understand the code better.

## Import Packages

To get started, you need to import the necessary packages in your C# project. Here’s how you can do it:

1. Open your Visual Studio project.
2. Right-click on your project in the Solution Explorer and select "Manage NuGet Packages."
3. Search for `Aspose.PDF` and install it.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Now that you have everything set up, let’s break down the process of removing hyperlinks from an HTML file after converting it to PDF.

## Step 1: Set Up the Document Directory

First things first, you need to specify the path to your documents directory. This is where your HTML file is located and where the output PDF will be saved.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where your HTML file is stored.

## Step 2: Load the HTML Document

Next, you will load the HTML document using the `Document` class from Aspose.PDF. This class allows you to work with PDF documents easily.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

Here, we are loading the HTML file named `SampleHtmlFile.html`. Make sure this file exists in your specified directory.

## Step 3: Save the Document to Memory Stream

Before we start processing the annotations, we need to save the document to a memory stream. This step is crucial as it prepares the document for further manipulation.

```csharp
doc.Save(new MemoryStream());
```

This line saves the document in memory, allowing us to work with it without writing it to disk just yet.

## Step 4: Iterate Through Annotations

Now, we will iterate through the annotations in the document. Annotations are elements like links, comments, and highlights. We are specifically interested in link annotations.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Process the link annotation
    }
}
```

In this loop, we check if the annotation type is a link. If it is, we proceed to the next steps.

## Step 5: Remove the Hyperlink Action

For each link annotation, we need to check if it has a hyperlink action. If it does, we will remove the hyperlink by setting its URI to an empty string.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

This code snippet ensures that the hyperlink action is effectively removed.

## Step 6: Absorb Text Fragments

Next, we will absorb the text fragments associated with the link annotation. This allows us to manipulate the text appearance.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

Here, we create a `TextFragmentAbsorber` and set its search options to the rectangle of the annotation. This helps us find the text that was linked.

## Step 7: Modify Text Appearance

Once we have the text fragments, we can modify their appearance. In this case, we will remove the underline and change the text color to black.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

This step enhances the readability of the text by removing the hyperlink styling.

## Step 8: Delete the Annotation

After modifying the text, we can safely delete the link annotation from the document.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

This line removes the hyperlink from the PDF, ensuring that it no longer exists in the final output.

## Step 9: Save the Modified Document

Finally, we need to save the modified document to a new PDF file. This is the last step in our process.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

This line saves the document with the hyperlinks removed, creating a new PDF file named `RemoveHyperlinksFromText_out.pdf`.

## Conclusion

And there you have it! You’ve successfully removed hyperlinks from an HTML document after converting it to PDF using Aspose.PDF for .NET. This process not only enhances the readability of your PDF but also gives you control over the content you present. 

## FAQ's

### Can I remove hyperlinks from any PDF document?
Yes, you can remove hyperlinks from any PDF document using Aspose.PDF for .NET.

### Is Aspose.PDF free to use?
Aspose.PDF offers a free trial, but for full features, you need to purchase a license. Check the [buy page](https://purchase.aspose.com/buy).

### What if I encounter issues while using Aspose.PDF?
You can seek help on the [support forum](https://forum.aspose.com/c/pdf/10).

### Can I convert other file formats to PDF using Aspose?
Yes, Aspose supports various file formats for conversion to PDF.

### Where can I download Aspose.PDF for .NET?
You can download it from the [download link](https://releases.aspose.com/pdf/net/).
