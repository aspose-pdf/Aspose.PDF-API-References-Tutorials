---
title: Highlight Character In PDF File
linktitle: Highlight Character In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to highlight characters in PDF file using Aspose.PDF for .NET.
type: docs
weight: 240
url: /ru/net/programming-with-text/highlight-character-in-pdf/
---
In this tutorial, we will explain how to highlight characters in a PDF file using the Aspose.PDF library for .NET. We will go through the step-by-step process of highlighting characters in a PDF using the provided C# source code.

## Requirements

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where your input PDF file is located. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the PDF Document

Next, we load the input PDF document using the `Aspose.Pdf.Document` class.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Step 3: Convert PDF to Image

To highlight characters, we convert the PDF document to an image using the `PdfConverter` class. We set the resolution for the conversion and retrieve the image as a `Bitmap` object.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Step 4: Highlight Characters

We loop through each page of the PDF document and use a `TextFragmentAbsorber` object to find all the words in the page. We then iterate over the text fragments, segments, and characters to highlight them using rectangles.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Set scale and transform
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Loop through pages
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Find all words in the page
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Loop through text fragments
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Highlight characters
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Loop through segments
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Highlight segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Loop through characters
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Highlightcharacter
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Step 5: Save the Output Image

Finally, we save the modified image with the highlighted characters to the specified output file.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Sample source code for Highlight Character In PDF using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Create TextAbsorber object to find all words
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Get the extracted text fragments
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Loop through the fragments
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

In this tutorial, you have learned how to highlight characters in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can highlight characters in a PDF and save the output as an image.

### FAQ's

#### Q: What is the purpose of the "Highlight Character In PDF File" tutorial?

A: The "Highlight Character In PDF File" tutorial explains how to use the Aspose.PDF library for .NET to highlight characters within a PDF document. The tutorial provides a step-by-step guide and C# source code to achieve this.

#### Q: Why would I want to highlight characters in a PDF document?

A: Highlighting characters in a PDF document can be useful for various purposes, such as emphasizing specific content or making certain text more visible and distinguishable.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where your input PDF file is located.

#### Q: How do I load the PDF document and convert it to an image?

A: In the tutorial, the `Aspose.Pdf.Document` class is used to load the input PDF document. Then, the `PdfConverter` class is employed to convert the PDF document to an image. The resolution of the image is set, and the image is retrieved as a `Bitmap` object.

#### Q: How do I highlight characters in the PDF document image?

A: The tutorial guides you through the process of looping through each page of the PDF document, finding words using a `TextFragmentAbsorber`, and iterating through text fragments, segments, and characters to highlight them using rectangles.

#### Q: Can I customize the appearance of the highlighted characters and segments?

A: Yes, you can customize the appearance of the highlighted characters and segments by modifying the colors and styles used in the drawing operations.

#### Q: How do I save the modified image with the highlighted characters?

A: The tutorial demonstrates how to save the modified image with the highlighted characters to the specified output file using the `Save` method of the `Bitmap` class.

#### Q: Is a valid Aspose License required for this tutorial?

A: Yes, a valid Aspose License is required for this tutorial to work correctly. You can purchase a full license or obtain a 30-day temporary license from the Aspose website.