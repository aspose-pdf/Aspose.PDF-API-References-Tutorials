---
title: Create Multi Column Pdf
linktitle: Create Multi Column Pdf
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a multi column PDF using Aspose.PDF for .NET.
type: docs
weight: 110
url: /tr/net/programming-with-text/create-multi-column-pdf/
---
This tutorial will guide you through the process of creating a multi column PDF using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to create a multi column PDF, add the following using directives at the top of the file:

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

## Step 5: Set the page margins
Specify the left and right margin information for the PDF file using the `PageInfo.Margin` property of the `Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Step 6: Add a page to the document
Add a new page to the document using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Page page = doc.Pages.Add();
```

## Step 7: Create a Graph object and add a line
Create a new `Graph` object with specific dimensions and add a line to it. Then, add the `Graph` object to the `Paragraphs` collection of the page.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Step 8: Add heading text with HTML formatting
Create an `HtmlFragment` object and set its content to the desired HTML text. Then, add the fragment to the `Paragraphs` collection of the page.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Step 9: Create a FloatingBox with multiple columns
Create a `FloatingBox` object and set the number of columns and column spacing. Then, add text fragments and a line to the `Paragraphs` collection of the `FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Step 10: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object.

```csharp
doc.Save(dataDir);
```

### Sample source code for Create Multi Column Pdf using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Specify the left margin info for the PDF file
doc.PageInfo.Margin.Left = 40;
// Specify the Right margin info for the PDF file
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Add the line to paraphraphs collection of section object
page.Paragraphs.Add(graph1);
// Specify the coordinates for the line
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Create string variables with text containing html tags
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Create text paragraphs containing HTML text
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Add four columns in the section
box.ColumnInfo.ColumnCount = 2;
// Set the spacing between the columns
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Create a graphs object to draw a line
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Specify the coordinates for the line
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Add the line to paragraphs collection of section object
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Save PDF file
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Conclusion
You have successfully created a multi column PDF using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.

### FAQ's

#### Q: What is the focus of this tutorial?

This tutorial is focused on guiding you through the process of creating a multi-column PDF using the Aspose.PDF for .NET library. The provided C# source code demonstrates the necessary steps to achieve this.

#### Q: Which namespaces should I import for this tutorial?

A: In the code file where you want to create a multi-column PDF, import the following namespaces at the beginning of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q: How do I specify the document directory?

A: In the code, find the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How do I create a new Document instance?

A: In Step 4, you'll instantiate a new `Document` object using the provided code.

#### Q: How do I set the page margins?

A: In Step 5, you'll use the `PageInfo.Margin` property of the `Document` to specify the left and right margin information for the PDF file.

#### Q: How do I add a page to the document?

A: In Step 6, you'll add a new page to the document using the `Add` method of the `Pages` collection.

#### Q: How do I create a Graph object and add a line?

A: In Step 7, you'll create a new `Graph` object, add a line to it, and then add the `Graph` object to the `Paragraphs` collection of the page.

#### Q: How do I add heading text with HTML formatting?

A: In Step 8, you'll create an `HtmlFragment` object and set its content to the desired HTML text, then add the fragment to the `Paragraphs` collection of the page.

#### Q: How do I create a FloatingBox with multiple columns?

A: In Step 9, you'll create a `FloatingBox` object with multiple columns and column spacing, then add text fragments and a line to the `Paragraphs` collection of the `FloatingBox`.

#### Q: How do I save the PDF document?

A: In Step 10, you'll save the PDF document using the `Save` method of the `Document` object.

#### Q: What is the main takeaway from this tutorial?

A: By following this tutorial, you've learned how to create a multi-column PDF document using Aspose.PDF for .NET. This can be useful for displaying content in a structured and organized layout.