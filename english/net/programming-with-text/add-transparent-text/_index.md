---
title: Add Transparent Text
linktitle: Add Transparent Text
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add transparent text to a PDF document using Aspose.PDF for .NET.
type: docs
weight: 100
url: /net/programming-with-text/add-transparent-text/
---

This tutorial will guide you through the process of adding transparent text to a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add transparent text, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a new Document instance
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document doc = new Document();
```

## Step 5: Add a page to the document
Add a new page to the document by using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Step 6: Create a Graph object
Create a new `Graph` object with a specific width and height.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Step 7: Create a rectangle with transparency
Create a rectangle with specific dimensions and set its fill color to a transparent color using the `Color.FromRgb` method.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Step 8: Add the Graph object to the page
Add the `Graph` object to the paragraphs collection of the page.

```csharp
page.Paragraphs.Add(canvas);
```

## Step 9: Set position for the Graph object
Set the `IsChangePosition` property of the `Graph` object to `false` to prevent it from changing position.

```csharp
canvas. IsChangePosition = false;
```

## Step 10: Create a TextFragment with transparency
Create a `TextFragment` object and set its content to the desired text. Set the `ForegroundColor` property of the `TextState` to a color with transparency using the `Color.FromArgb` method.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Step 11: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Sample source code for Add Transparent Text using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Document instance
Document doc = new Document();
// Create page to pages collection of PDF file
Aspose.Pdf.Page page = doc.Pages.Add();
// Create Graph object 
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Create rectangle instance with certain dimensions
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Create color object from Alpha color channel
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Add rectanlge to shapes collection of Graph object
canvas.Shapes.Add(rect);
// Add graph object to paragraphs collection of page object
page.Paragraphs.Add(canvas);
// Set value to not change position for graph object
canvas.IsChangePosition = false;
// Create TextFragment instance with sample value
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Create color object from Alpha channel
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Set color information for text instance
text.TextState.ForegroundColor = color;
// Add text to paragraphs collection of page instance
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Conclusion
You have successfully added transparent text to your PDF document using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.
