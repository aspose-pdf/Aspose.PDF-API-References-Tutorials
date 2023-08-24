---
title: Add Drawing In PDF File
linktitle: Add Drawing In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add drawing in PDF file using Aspose.PDF for .NET. Follow this step-by-step guide to create attractive PDF documents with drawing features.
type: docs
weight: 10
url: /es/net/programming-with-graphs/add-drawing/
---
Application development often requires adding features such as drawings and graphics to make documents more attractive and informative. In this article, we will guide you step by step to explain the C# source code to add drawing to programming with graphics using Aspose.PDF for .NET.

Before you start, make sure you have installed the Aspose.PDF library and set up your development environment. Also, make sure you have basic knowledge of C# programming.

## Step 1: Introduction to Aspose.PDF for .NET and its features

Aspose.PDF is a powerful and versatile library for creating, manipulating and converting PDF files in .NET applications. It offers a wide range of features for working with PDF documents, including adding drawings, graphics, text, etc.

## Step 2: Understand the source code to add drawings using Aspose.PDF

The provided source code uses the Aspose.PDF library to create a simple drawing in a PDF document. We will now examine each step of the code in detail.

## Step 3: Configuring the documents directory and initializing the variables

In the source code, you need to specify the directory where you want to save the resulting PDF file. You can modify the "dataDir" variable to indicate the desired directory.

Additionally, the code initializes variables for the alpha, red, green, and blue color components.

## Step 4: Creating a Color Object with Alpha RGB

The following line of code creates a Color object using the specified alpha, red, green, and blue values:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

This allows to define a color with an alpha channel, which means that the color can be partially transparent.

## Step 5: Instantiating a Document Object

To start working with Aspose.PDF, we need to create an instance of the Document class. This represents our PDF document.

```csharp
Document document = new Document();
```

## Step 6: Adding a page to the PDF file

We need to add a page to the PDF file where we want to display our drawing.

```csharp
Page page = document.Pages.Add();
```

## Step 7: Creating a Graph Object with Dimensions

In this step, we create a Graph object with specified dimensions. This object will serve as a container for our drawing.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## Step 8: Setting the border for the Drawing object

We can set the border of the Drawing object using the BorderInfo class.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

This will set a black border around our drawing.

## Step 9: Adding the graph object to the page

Now we add the graph object to the paragraphs collection of the Page class instance.

```csharp
page.Paragraphs.Add(graph);
```

## Step 10: Creating a Rectangle Object with Dimensions

We create a Rectangle object with specified dimensions. This rectangle will be added to our drawing.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## Step 11: Creating a GraphInfo object for the Rectangle instance

We need to create a GraphInfo object for the Rectangle instance to configure its graph properties.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## Step 12: Configuring color information for the GraphInfo object

We can configure the color information for the GraphInfo object using the Color and FillColor properties.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

This will set the rectangle border color to red and the fill color to the specified alpha color.

## Step 13: Adding the rectangle shape to the graph object

Now we add the rectangle shape to the shape collection of the graph object.

```csharp
graph.Shapes.Add(rectangle);
```
## Step 14: Save PDF file and display success message

Finally, we save the PDF file and display a message that the drawing was added successfully.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### Sample source code for Add Drawing using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// Create Color object using Alpha RGB 
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // Provide alpha channel
// Instantiate Document object
Document document = new Document();
// Add page to pages collection of PDF file
Page page = document.Pages.Add();
// Create Graph object with certain dimensions
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// Set border for Drawing object
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// Add graph object to paragraphs collection of Page instance
page.Paragraphs.Add(graph);
// Create Rectangle object with certain dimensions
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// Create graphInfo object for Rectangle instance
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// Set color information for GraphInfo instance
graphInfo.Color = (Aspose.Pdf.Color.Red);
// Set fill color for GraphInfo
graphInfo.FillColor = (alphaColor);
// Add rectangle shape to shapes collection of graph object
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// Save PDF file
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## Conclusion

In this article, we learned how to add drawing to programming with graphics using Aspose.PDF for .NET. We followed a step-by-step guide to understand the source code and the various steps involved in adding a drawing to a PDF file. Using the powerful features of Aspose.PDF, you can create attractive and interactive PDF documents in your .NET applications.


### FAQ's for add drawing in PDF file

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables the creation, manipulation, and conversion of PDF files within .NET applications.

#### Q: Can I adjust the transparency of colors in my drawings?

A: Yes, by using the alpha channel in the Color object, you can create partially transparent colors for your drawings.

#### Q: How do I add a border to a drawing in a PDF document?

A: You can set the border of a Drawing object using the BorderInfo class, allowing you to define border properties such as color and style.

#### Q: Is Aspose.PDF suitable for beginners in C# programming?

A: Aspose.PDF offers a wide range of features, including drawing, and may require a basic understanding of C# programming to fully utilize its capabilities.