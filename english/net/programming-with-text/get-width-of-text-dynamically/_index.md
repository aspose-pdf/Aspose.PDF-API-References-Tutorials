---
title: Get Width Of Text Dynamically
linktitle: Get Width Of Text Dynamically
second_title: Aspose.PDF for .NET API Reference
description: Learn how to dynamically get the width of text using Aspose.PDF for .NET.
type: docs
weight: 220
url: /net/programming-with-text/get-width-of-text-dynamically/
---

Here's a step-by-step guide to explaining the provided C# source code, which uses Aspose.PDF for .NET to get the width of text dynamically:

## Step 1: Initialize the `dataDir` variable with the path to your document directory. This is where the input documents or resources are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory path.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Find the font you want to use for measuring the text width. In this code snippet, the font "Arial" is used.

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

## Step 3: Create a new `TextState` object to define the text state properties, such as font and font size.

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

## Step 4: Verify the accuracy of font measurement for a specific character and font size combination. In this case, the character "A" is measured with a font size of 14. If the measured width does not match the expected value (9.337), an error message is displayed.

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
Console.WriteLine("Unexpected font string measure!");
```

## Step 5: Verify the accuracy of text state measurement for a specific character. In this case, the character "z" is measured. If the measured width does not match the expected value (7.0), an error message is displayed.

```csharp
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
Console.WriteLine("Unexpected font string measure!");
```

## Step 6: Iterate through each character from 'A' to 'z' and compare the font measurement with the text state measurement. If they don't match, an error message is displayed. This loop ensures consistency between font measurement and text state measurement for each character.

```csharp
for (char c = 'A'; c <= 'z'; c++)
{
double fnMeasure = font.MeasureString(c.ToString(), 14);
double tsMeasure = ts.MeasureString(c.ToString());
if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
Console.WriteLine("Font and state string measuring doesn't match!");
}
```

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

This C# source code demonstrates how to use Aspose.PDF for .NET to get the width of text dynamically. By comparing font measurements with text state measurements, you can ensure accurate and consistent results when working with text in PDF documents.
