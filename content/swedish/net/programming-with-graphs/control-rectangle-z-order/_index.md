---
title: Control Rectangle Z Order In PDF File
linktitle: Control Rectangle Z Order In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to control the Z-order of rectangles in a PDF file using Aspose.PDF for .NET. 
type: docs
weight: 40
url: /sv/net/programming-with-graphs/control-rectangle-z-order/
---
In this tutorial, we will walk you through the following C# source code step by step to control the Z-order of rectangles using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

## Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where you want to save the resulting PDF file. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Instantiating a Document Object and Adding a Page

We create an instance of the Document class and add a page to this document.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Step 3: Setting up the page size

We set the PDF page size using the SetPageSize method.

```csharp
page1.SetPageSize(375, 300);
```

## Step 4: Setting Page Margins

We can configure the page margins using the properties of the PageInfo object.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Step 5: Add Rectangles with Specified Z Order

We create and add rectangles to the page with different colors and specified Z orders.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Step 6: Saving the Resulting PDF File

Finally, we save the resulting PDF file with the name "ControlRectangleZOrder_out.pdf" in the specified directory.

```csharp
doc1.Save(dataDir);
```
### Sample source code for Control Rectangle Z Order using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document class object
Document doc1 = new Document();
/// Add page to pages collection of PDF file
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Set size of PDF page
page1.SetPageSize(375, 300);
// Set left margin for page object as 0
page1.PageInfo.Margin.Left = 0;
// Set top margin of page object as 0
page1.PageInfo.Margin.Top = 0;
// Create a new rectangle with Color as Red, Z-Order as 0 and certain dimensions
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Create a new rectangle with Color as Blue, Z-Order as 0 and certain dimensions
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Create a new rectangle with Color as Green, Z-Order as 0 and certain dimensions
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Save resultant PDF file
doc1.Save(dataDir);

```

## Conclusion

In this tutorial, we explained how to control the Z-order of rectangles using Aspose.PDF for .NET. You can now use this knowledge to arrange and layer rectangles in your PDF files with precision.

### FAQ's control rectangle z order in PDF file

#### Q: What is the purpose of this tutorial?

A: This tutorial aims to guide you through the process of controlling the Z-order of rectangles using Aspose.PDF for .NET, allowing you to arrange and layer rectangles in your PDF files.

#### Q: What prerequisites are required before starting?

A: Before you begin, ensure that you have installed the Aspose.PDF library and set up your development environment. Additionally, having a basic understanding of C# programming is recommended.

#### Q: How do I specify the directory for saving the PDF file?

A: In the provided source code, you can modify the "dataDir" variable to indicate the directory where you want to save the resulting PDF file.

#### Q: What is the purpose of setting page size and margins?

A: Setting the page size and margins helps configure the layout of the PDF page and provides a canvas on which you can arrange the rectangles.

#### Q: How do I add rectangles with specified Z order?

A: You can create and add rectangles to the page using the `AddRectangle` method, specifying the position, dimensions, color, and Z order for each rectangle.

#### Q: What is Z-order, and why is it important?

A: Z-order determines the stacking order of objects on a page. Objects with higher Z-order values are positioned on top of objects with lower Z-order values, affecting their visibility and layering.

#### Q: Can I customize the colors and dimensions of the rectangles?

A: Yes, you can customize the colors, positions, and dimensions of the rectangles by modifying the parameters passed to the `AddRectangle` method.

#### Q: How do I save the resulting PDF file after arranging the rectangles?

A: After arranging the rectangles, you can save the resulting PDF file using the `doc1.Save(dataDir);` line in the provided source code.