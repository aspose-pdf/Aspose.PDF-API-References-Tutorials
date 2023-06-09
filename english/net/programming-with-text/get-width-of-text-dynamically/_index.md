---
title: Get Width Of Text Dynamically
linktitle: Get Width Of Text Dynamically
second_title: Aspose.PDF for .NET API Reference
description: Learn how to dynamically get the width of text using Aspose.PDF for .NET.
type: docs
weight: 220
url: /net/programming-with-text/get-width-of-text-dynamically/
---

In this tutorial, we will explain how to use Aspose.PDF for .NET to dynamically measure the width of text in C#. This can be useful when you need to determine the size of a text string before rendering it on a PDF document. We will guide you through the provided C# source code step by step.

## Prerequisites

Before you begin, make sure you have the following:

- Aspose.PDF for .NET library installed.
- Visual Studio or any other C# development environment.

## Step 1: Set the Document Directory

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are located. This will be used to store any generated PDF files.

## Step 2: Find the Font

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

The code above finds the Arial font using the `FindFont` method from the `FontRepository` class. If you want to use a different font, replace `"Arial"` with the desired font name.

## Step 3: Set the Text State

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

Here, we create a new `TextState` object and set its properties. We assign the previously found font (`font`) and set the font size to 14. Adjust the font size as needed.

## Step 4: Measure the Width of Text

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```

The code above demonstrates how to measure the width of text using both the font directly (`font.MeasureString`) and the text state (`ts.MeasureString`). It includes some validation checks to ensure the measurements are accurate.

### Sample source code for Get Width Of Text Dynamically using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```


## Conclusion

You have learned how to use Aspose.PDF for .NET to dynamically measure the width of text in C#. By following the steps outlined in this tutorial, you can accurately determine the width of text strings before rendering them in a PDF document.
