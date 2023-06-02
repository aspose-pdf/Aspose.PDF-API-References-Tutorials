---
title: Determine Progress
linktitle: Determine Progress
second_title: Aspose.PDF for .NET API Reference
description: Learn how to determine the progress of a PDF document's conversion process using Aspose.PDF for .NET with this step-by-step guide and code example.
type: docs
weight: 110
url: /content/net/programming-with-document/determineprogress/
---

Aspose.PDF for .NET provides a feature that allows you to determine the progress of a PDF document's conversion process. In this tutorial, we will provide a step-by-step guide on how to implement this feature using C# and Aspose.PDF for .NET.

## Step 1: Loading the PDF document

The first step is to load the PDF document that you want to convert. For this tutorial, we will use the file "AddTOC.pdf". Replace the path to this file with the path to your own PDF document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## Step 2: Setting up the custom progress handler

Next, we need to set up the custom progress handler that will be called during the conversion process. In this tutorial, we will use the `ConversionProgressEventHandler` delegate provided by Aspose.PDF for .NET.

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## Step 3: Saving the PDF document

Finally, we need to save the PDF document using the `Save()` method of the `Document` object. We will pass in the custom progress handler that we set up in the previous step as a parameter.

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## Step 4: Implementing the progress handler

To implement the progress handler, we need to define a method that takes a single parameter of type `ConversionProgressEventArgs`. This method will be called during the conversion process to report the progress of the conversion.

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### Example source code for Determine Progress using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## Conclusion

In this tutorial, we have provided a step-by-step guide on how to determine the progress of a PDF document's conversion process using Aspose.PDF for .NET. We have also provided a code example that you can use as a reference when implementing this feature in your own application.