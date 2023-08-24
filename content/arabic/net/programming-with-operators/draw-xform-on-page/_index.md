---
title: Draw XForm On Page
linktitle: Draw XForm On Page
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to drawing an XForm form on a PDF page using Aspose.PDF for .NET. Add and position the form on the page.
type: docs
weight: 10
url: /ar/net/programming-with-operators/draw-xform-on-page/
---
In this tutorial, we will provide you with a step-by-step guide on how to draw an XForm on a page using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows you to create, manipulate and convert PDF documents programmatically. Using the operators provided by Aspose.PDF, you can add and position an XForm form on an existing PDF page.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Visual Studio installed with .NET framework.
2. The Aspose.PDF library for .NET.

## Step 1: Project Setup

To get started, create a new project in Visual Studio and add a reference to the Aspose.PDF for .NET library. You can download the library from Aspose official website and install it on your machine.

## Step 2: Import the necessary namespaces

In your C# code file, import the namespaces required to access the classes and methods provided by Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Step 3: Setting file paths

Define the file paths for the background image, the input PDF file and the output PDF file:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Be sure to specify the actual file paths on your machine.

## Step 4: Loading the input PDF file

Use the following code to load the input PDF file:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// The following code uses the GSave/GRestore operators
// The code uses the ContatenateMatrix operator to position the XForm
// The code uses the Do operator to draw the XForm on the page
// GSave/GRestore operators wrap existing content
// this is done to get the initial graphics state at the end of the existing content
// otherwise there may be unwanted transformations left at the end of the chain of existing operators
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Add GSave operator to properly reset graphics state after new commands
pageContents. Add(new GSave());

// Create the XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Set the width and height of the image
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Load the image into a stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Add the image to the XForm resource images collection
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Using the Do operator: this operator draws the image
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Position the XForm at coordinates x=100 and y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Draw the XForm with the Do operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Position the XForm at coordinates x=100 and y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Draw the XForm with the Do operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Restore graphics state with GRestore after GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Be sure to specify the actual file paths and adjust the page number and XForm positions as needed.

### Sample source code for Draw XForm On Page using Aspose.PDF for .NET
 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// The sample demonstrates 
	// GSave/GRestore operators usage
	// ContatenateMatrix operator usage to position xForm
	// Do operator usage to draw xForm on page
	// Wrap existing contents with GSave/GRestore operators pair
	//        this is to get initial graphics state at the and of existing contents
	//        otherwise there might remain some undesirable transformations at the end of existing operators chain
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Add save graphics state operator to properly clear graphics state after new commands
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Create xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Define image width and heigh
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Load image into stream
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Add image to Images collection of the XForm Resources
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Using Do operator: this operator draws image
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Place form to the x=100 y=500 coordinates
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Draw form with Do operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Place form to the x=100 y=300 coordinates
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Draw form with Do operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Restore grahics state with GRestore after the GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusion

In this tutorial, you learned how to draw an XForm form on a PDF page using Aspose.PDF for .NET. By following the steps described, you will be able to add and position an XForm form on an existing page, thus giving more flexibility to your PDF documents.

### FAQ's for draw XForm on page

#### Q: What is an XForm in Aspose.PDF?

A: An XForm is a reusable graphical object in a PDF document. It allows you to define and draw complex graphics, images, or text that can be reused multiple times on different pages.

#### Q: How do I import the necessary namespaces for Aspose.PDF?

A: In your C# code file, use the `using` directive to import the required namespaces for accessing the classes and methods provided by Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q: What is the purpose of the GSave and GRestore operators?

A: The `GSave` and `GRestore` operators in Aspose.PDF are used to save and restore the graphics state. They help ensure that transformations and settings applied to one section of the content do not affect subsequent sections.

#### Q: How do I define an XForm using Aspose.PDF?

A: To create an XForm, use the `XForm.CreateNewForm` method and add it to the `Resources.Forms` collection of a specific page. You can then add content to the XForm's `Contents` property.

#### Q: How can I draw an image within an XForm?

A: Load the image into a stream and add it to the `Resources.Images` collection of the XForm. Use the `Do` operator within the XForm's `Contents` to draw the image.

#### Q: How do I position an XForm on a PDF page?

A: To position an XForm on a page, use the `ConcatenateMatrix` operator within the page's `Contents`. Adjust the matrix parameters to specify the translation (position) and scaling of the XForm.

#### Q: Can I draw multiple XForms on the same page?

A: Yes, you can draw multiple XForms on the same page by adjusting the `ConcatenateMatrix` parameters to position each XForm at different coordinates.

#### Q: Can I modify the content of an XForm after it's created?

A: Yes, you can modify an XForm's contents after creation by adding additional operators to its `Contents` property.

#### Q: What happens if I omit the GSave and GRestore operators?

A: Omitting the GSave and GRestore operators may lead to unwanted transformations or settings being applied to subsequent content. Using them helps maintain a clean graphics state.

#### Q: Can I reuse XForms across different pages of the PDF document?

A: Yes, you can reuse XForms on multiple pages by adding the same XForm to the `Resources.Forms` collection of different pages.

#### Q: Is there a limit to the number of XForms I can create?

A: While there is no strict limit to the number of XForms you can create, keep in mind that too many XForms may impact performance and memory usage. Use them judiciously.

#### Q: Can I rotate an XForm or apply other transformations?

A: Yes, you can use the `ConcatenateMatrix` operator to apply transformations such as rotation, scaling, and translation to an XForm.
