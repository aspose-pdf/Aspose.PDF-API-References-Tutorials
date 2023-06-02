---
title: Update Free Text Annotation
linktitle: Update Free Text Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to update free text annotation feature of Aspose.PDF for .NET using C# source code.
type: docs
weight: 160
url: /net/annotations/updatefreetextannotation/
---
In this article, we will provide a step-by-step guide to explain the following C# source code of Update Free Text Annotation feature of Aspose.PDF for .NET. We will go through each line of code and explain what it does, so even beginners can understand it.

Now let's explain each line of the code above step by step:

## Step 1: Setting the document directory

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

In this line, we are setting the path to the directory that contains the PDF document that we want to update.

## Step 2: Opening the PDF document

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

Here we are opening the PDF document using Aspose.PDF's `Document` class and specifying the path to the input PDF file.

## Step 3: Updating the font size and color of the free text annotation

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

In this step, we are updating the font size and color of the first free text annotation on the second page of the PDF document. We are doing this by accessing the `TextStyle` property of the `FreeTextAnnotation` object and setting its `FontSize` and `Color` properties to 18 and Green, respectively.

## Step 4: Handling Exceptions

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

This is a standard `try-catch` block that catches any exceptions that may occur while executing the code and prints the error message to the console.

### Example source code for Update Free Text Annotation using Aspose.PDF for .NET

Before diving into the explanation of the code, let's first take a look at the code itself. This code example shows how to update the properties of a free text annotation in a PDF document using Aspose.PDF for .NET.

```csharp
try
{
    // The path to the documents directory.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Open document
    Document doc1 = new Document(dataDir + "input.pdf");

    // Set font size and color of the annotation:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

## Conclusion

In this article, we have provided a step-by-step guide to explain the C# source code of the Update Free Text Annotation feature of Aspose.PDF for .NET. By following these steps, you can easily update the font size and color of free text annotations in your PDF documents using Aspose.PDF for .NET.
