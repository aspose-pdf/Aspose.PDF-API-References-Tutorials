---
title: Convert From RGB To Grayscale
linktitle: Convert From RGB To Grayscale
second_title: Aspose.PDF for .NET API Reference
description: Learn how to convert PDFs from RGB to Grayscale using Aspose.PDF for .NET. Enhance printing quality and reduce file size.
type: docs
weight: 60
url: /content/net/programming-with-document/convertfromrgbtograyscale/
---

In this tutorial, we will guide you through the process of converting a PDF document from RGB colorspace to Grayscale using Aspose.PDF for .NET. This conversion can be useful for various purposes, such as reducing file size or preparing documents for printing. Follow the step-by-step guide below:

## Step 1: Load the source PDF file

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Your code here...
}
```

## Step 2: Set the conversion strategy

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## Step 3: Convert each page to grayscale

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## Step 4: Save the resultant file

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

Congratulations! You have successfully converted the PDF document from RGB to Grayscale using Aspose.PDF for .NET.

### Example source code for Convert From RGB to Grayscale using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load source PDF file
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Now you can easily convert your PDF documents from RGB to Grayscale using Aspose.PDF for .NET.

