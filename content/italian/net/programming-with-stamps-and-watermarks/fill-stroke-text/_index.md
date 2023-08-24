---
title: Fill Stroke Text In PDF File
linktitle: Fill Stroke Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily fill and outline text in PDF file with Aspose.PDF for .NET.
type: docs
weight: 90
url: /it/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In this tutorial, we will take you step by step on how to fill and outline text in PDF file using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to apply fill and outline colors to text in the PDF file.

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

### FAQ's for fill stroke text in PDF file

#### Q: What does it mean to fill and outline text in a PDF document, and when might I need to do so?

A: Filling and outlining text in a PDF document involves applying colors to the interior of the text characters (fill) and to the borders around the text (outline). This can be used to enhance the visual appearance of the text, create emphasis, or highlight specific content within the PDF.

#### Q: How does the provided C# source code accomplish filling and outlining text in a PDF file?

A: The provided source code demonstrates how to create a `TextState` object to define advanced text properties, such as outline color and rendering mode. It then uses Aspose.PDF.Facades to load an existing PDF document, create a stamp containing the text with specified fill and stroke properties, and add the stamp to the document.

#### Q: What is the purpose of the `TextState` object in the code?

A: The `TextState` object is used to define advanced text properties, including the color of the text outline (stroke) and the rendering mode. It allows you to customize how the text appears in terms of stroke and fill.

#### Q: Can I apply different fill and outline colors to different parts of the same text?

A: Yes, you can modify the code to create different `TextState` objects with distinct fill and outline colors and apply them to specific parts of the text using separate `Stamp` objects.

#### Q: Can I apply fill and outline colors to text that is already present in the PDF document?

A: Yes, you can use similar principles to apply fill and outline colors to existing text in the PDF document by selecting the appropriate text objects and adding them as stamps with the desired `TextState` properties.

#### Q: How can I adjust the opacity and blending of the filled and outlined text?

A: The provided code allows you to set the opacity and blending properties of the stamp using the `Opacity` and `BlendingSpace` properties, respectively. You can adjust these values to achieve the desired visual effect.

#### Q: How can I apply different fill and outline colors to multiple stamps within the same PDF document?

A: You can create multiple `TextState` objects with different fill and outline colors, and then create separate `Stamp` objects for each set of text with distinct colors. Add these stamps to the same PDF document using the `PdfFileStamp` class.

#### Q: Can I use fonts other than Arial for the outlined and filled text?

A: Yes, you can change the font by modifying the font name parameter in the `FormattedText` constructor when creating the stamp. You can use any font available on your system.

#### Q: How can I modify the rotation angle of the outlined and filled text?

A: The provided code allows you to set the rotation angle of the stamp using the `Rotation` property. You can adjust this property to specify the desired rotation angle for the text.

#### Q: How can I control the position and size of the outlined and filled text on the page?

A: You can use the `SetOrigin` method of the `Stamp` object to set the X and Y coordinates of the stamp's position on the page. Additionally, you can adjust the font size in the `FormattedText` constructor to control the size of the text.