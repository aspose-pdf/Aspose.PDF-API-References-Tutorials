---
title: Create Multilayer PDF First Approach
linktitle: Create Multilayer PDF First Approach
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create multilayer PDF documents using the First Approach with Aspose.PDF for .NET. Add text, images, and more to enhance your PDFs.
type: docs
weight: 70
url: /net/programming-with-document/createmultilayerpdffirstapproach/
---

In this tutorial, we will guide you through the process of creating a multilayer PDF using the first approach with Aspose.PDF for .NET. This approach allows you to add multiple layers to your PDF document. Follow the step-by-step guide below:

## Step 1: Initialize the PDF document

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Step 2: Add a new page to the document

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Step 3: Add a text fragment to the page

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Step 4: Customize the text fragment

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Step 5: Add an image to the page

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Step 6: Add a floating box to the page

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Step 7: Save the resultant PDF document

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Congratulations! You have successfully created a multilayer PDF document using the first approach with Aspose.PDF for .NET.

Example source code for Create Multilayer PDF First Approach using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Now you can create multilayer PDF documents using the first approach with Aspose.PDF for .NET.

