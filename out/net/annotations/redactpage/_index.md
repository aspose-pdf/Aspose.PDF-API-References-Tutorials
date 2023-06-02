---
title: Redact Page
linktitle: Redact Page
second_title: Aspose.PDF for .NET API Reference
description: This article explains how to redact a PDF page using Aspose.PDF for .NET, including step-by-step instructions and example source code.
type: docs
weight: 120
url: /content/net/annotations/redactpage/
---
If you're looking to redact sensitive information from a PDF document using Aspose.PDF for .NET, you're in luck! Here's a step-by-step guide to get you started:

## Step 1: In the code, set the path to the directory where your PDF document is located:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Step 3: Create a RedactionAnnotation instance for a specific page region:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Step 4: Set the fill color, border color, and text color of the redaction annotation:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Step 5: Set the text to be printed on the redaction annotation and its alignment:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Step 6: Repeat the overlay text over the redaction annotation:

```csharp
annot.Repeat = true;
```

## Step 7: Add the annotation to the annotations collection of the first page:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Step 8: Flatten the annotation and redact page contents, i.e., remove text and images under the redacted annotation:

```csharp
annot.Redact();
```

## Step 9: Set the path and name of the output PDF file:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Step 10: Save the PDF document with the redacted page:

```csharp
doc.Save(dataDir);
```

That's it! You have successfully redacted a page of your PDF document using Aspose.PDF for .NET.

### Example source code for Redact Page using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document doc = new Document(dataDir + "input.pdf");

// Create RedactionAnnotation instance for specific page region
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Text to be printed on redact annotation
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Repat Overlay text over redact Annotation
annot.Repeat = true;
// Add annotation to annotations collection of first page
doc.Pages[1].Annotations.Add(annot);
// Flattens annotation and redacts page contents (i.e. removes text and image
// Under redacted annotation)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```