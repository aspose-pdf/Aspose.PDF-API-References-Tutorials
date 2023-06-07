---
title: Fill Stroke Text
linktitle: Fill Stroke Text
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily fill and outline text in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 90
url: /net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In this tutorial, we will take you step by step on how to fill and outline text in a PDF document using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to apply fill and outline colors to text in the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Creating the TextState Object

The first step is to create a TextState object to pass the advanced properties. Here's how:

```csharp
// Create TextState object to transfer advanced properties
TextState ts = new TextState();

// Set outline color
ts.StrokingColor = Color.Gray;

// Define the text rendering mode
ts.RenderingMode = TextRenderingMode.StrokeText;
```

The above code creates a new TextState object and sets the outline color as well as how the text is rendered.

## Step 3: Loading the PDF document

Now that the TextState object is ready, we can load the PDF document where we want to apply the text fill and outline. Here's how:

```csharp
// Load the PDF document as input
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

The code above loads the existing PDF document using the PdfFileStamp class from the Aspose.PDF.Facades library.

## Step 4: Add Fill and Stroke to Text

Now that the PDF document is loaded, we can add the fill and outline to the text. Here's how:

```csharp
// Create a stamp (Stamp) with the defined text and properties
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind the TextState object
stamp.BindTextState(ts);

// Set origin X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Add the stamp to the document
fileStamp.AddStamp(stamp);
```

The above code creates a Stamp with the specified text and defined Fill and Stroke properties.

## Step 5: Save the output document

Once the text stamp is added, we can save the modified PDF document. Here's how:

```csharp
// Save the modified document
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Fill Stroke Text using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create TextState object to transfer advanced properties
TextState ts = new TextState();

// Set color for stroke
ts.StrokingColor = Color.Gray;

// Set text rendering mode
ts.RenderingMode = TextRenderingMode.StrokeText;

// Load an input PDF document
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind TextState
stamp.BindTextState(ts);

// Set X,Y origin
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Add Stamp
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Conclusion

Congratulation ! You have learned how to fill and outline text in a PDF document using Aspose.PDF for .NET. Now you can apply this knowledge to customize fill and outline colors in your PDF documents.

