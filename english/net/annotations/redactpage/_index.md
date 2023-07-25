---
title: Redact Page
linktitle: Redact Page
second_title: Aspose.PDF for .NET API Reference
description: This article explains how to redact a PDF page using Aspose.PDF for .NET, including step-by-step instructions and example source code.
type: docs
weight: 120
url: /net/annotations/redactpage/
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

## Conclusion

In this tutorial, we explored how to redact a page in a PDF document using Aspose.PDF for .NET. Redaction is an essential feature for securely removing sensitive information from PDF documents, ensuring data privacy and security. By following the step-by-step guide and using the provided C# source code, developers can easily add redaction functionality to their applications, improving the data security and compliance of their PDF documents. Aspose.PDF for .NET offers a robust set of tools for working with PDF files, providing efficient and effective redaction capabilities along with various other PDF operations.

### FAQ's

#### Q: What is redaction in a PDF document?

A: Redaction in a PDF document is the process of permanently removing or obscuring sensitive or confidential information from the document. This ensures that the redacted information cannot be accessed or viewed, providing data security and privacy.

#### Q: Can I redact multiple areas of a page in a PDF document?

A: Yes, with Aspose.PDF for .NET, you can create multiple `RedactionAnnotation` instances to redact multiple areas of a page in a PDF document. Each `RedactionAnnotation` can be customized with different fill colors, border colors, overlay texts, and other properties.

#### Q: Does redaction in Aspose.PDF for .NET permanently remove the redacted information?

A: Yes, redaction in Aspose.PDF for .NET permanently removes the redacted information from the PDF document. Once redaction is performed and the document is saved, the redacted information cannot be recovered.

#### Q: Can I redact text and images under the redacted area in a PDF document?

A: Yes, when you call the `Redact()` method on the `RedactionAnnotation` object, it will not only add a redaction overlay to the specified area but also remove the underlying text and images from that area.

#### Q: Can Aspose.PDF for .NET redact multiple pages in a PDF document?

A: Yes, you can create `RedactionAnnotation` instances for multiple pages in a PDF document to redact sensitive information from multiple pages.
