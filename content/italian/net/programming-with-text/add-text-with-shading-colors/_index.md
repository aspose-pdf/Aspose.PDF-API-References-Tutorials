---
title: Add Text With Shading Colors In PDF File
linktitle: Add Text With Shading Colors In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add text with shading colors in PDF file using Aspose.PDF for .NET.
type: docs
weight: 80
url: /it/net/programming-with-text/add-text-with-shading-colors/
---
This tutorial will guide you through the process of adding text with shading colors in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add text with shading colors, add the following using directive at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Load the PDF document
Load the existing PDF document using the `Document` constructor and provide the path to the document file.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Code goes here...
}
```

## Step 5: Find the text to modify
Use `TextFragmentAbsorber` to find the desired text within the document. In the provided code, it looks for the text "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Step 6: Set shading color for the text
Create a new `Color` object with a pattern colorspace and specify the gradient shading colors. Assign this color to the `ForegroundColor` property of the `TextState` of the `TextFragment` object.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Step 7: Apply additional text formatting (optional)
You can apply additional formatting to the text fragment, such as underlining, by modifying the properties of the `TextState` object.

```csharp
textFragment.TextState.Underline = true;
```

## Step 8: Save the modified PDF document
Save the modified PDF document using the `Save` method of the `Document` object.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Sample source code for Add Text With Shading Colors using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Create new color with pattern colorspace
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusion
You have successfully added text with shading colors to your PDF document using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.

### FAQ's

#### Q: What is the main focus of this tutorial?

A: This tutorial guides you through the process of adding text with shading colors to a PDF file using the Aspose.PDF for .NET library. The provided C# source code demonstrates the necessary steps to achieve this.

#### Q: Which namespaces do I need to import for this tutorial?

A: In the code file where you want to add text with shading colors, import the following namespaces at the beginning of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### Q: How do I specify the document directory?

A: In the code, locate the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How do I load an existing PDF document?

A: In Step 4, you'll load an existing PDF document using the `Document` constructor and providing the path to the document file:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Code goes here...
}
```

#### Q: How do I find and modify specific text within the PDF document?

A: In Step 5, you'll use the `TextFragmentAbsorber` to find the desired text within the document. Then, you can modify its properties:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### Q: How can I set shading colors for the text?

A: In Step 6, you'll create a new `Color` object with a pattern colorspace and specify the gradient shading colors. Assign this color to the `ForegroundColor` property of the `TextState` of the `TextFragment` object:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### Q: Can I apply additional text formatting to the modified text?

A: Yes, in Step 7, you can apply additional text formatting such as underlining by modifying the properties of the `TextState` object:

```csharp
textFragment.TextState.Underline = true;
```

#### Q: How do I save the modified PDF document?

A: In Step 8, you'll save the modified PDF document using the `Save` method of the `Document` object:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### Q: What is the main takeaway from this tutorial?

A: By following this tutorial, you've successfully learned how to enhance your PDF document by adding text with shading colors using Aspose.PDF for .NET. This can be particularly useful for highlighting and emphasizing specific text content within your PDF files.