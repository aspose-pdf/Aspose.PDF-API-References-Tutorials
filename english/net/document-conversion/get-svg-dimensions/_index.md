---
title: Get SVG Dimensions
linktitle: Get SVG Dimensions
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to getting SVG dimensions using Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/document-conversion/get-svg-dimensions/
---

## Introduction
In this tutorial, we'll walk you through the process of getting the dimensions of an SVG file using Aspose.PDF for .NET. SVG (Scalable Vector Graphics) is an XML-based image format used to represent vector graphics. Using the steps below, you will be able to get the dimensions of an SVG file and save them as a PDF.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading SVG file
In this step, we will load the SVG file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your SVG file is located.

## Step 2: Page size adjustment
Now that we've loaded the SVG file, we can adjust the page size to accommodate the SVG content. Use the following code:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

The code above sets the page margins to zero, allowing the page size to adjust based on the SVG content.

## Step 3: Saving the resulting PDF
After adjusting the page size, we can now save the resulting PDF document. Here is the last step:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the desired directory where you want to save the output PDF file.
  
### Example source code for Get SVG Dimensions using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Conclusion
In this tutorial, we've covered the step-by-step process of getting the dimensions of an SVG file using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to get the dimensions of an SVG file and save them to the PDF Format. This feature can be useful when you need to measure the dimensions of a vector graphic.


