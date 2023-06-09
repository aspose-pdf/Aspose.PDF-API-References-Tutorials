---
title: Image Information
linktitle: Image Information
second_title: Aspose.PDF for .NET API Reference
description: Extract image information in a PDF file using Aspose.PDF for .NET.
type: docs
weight: 160
url: /content/net/programming-with-images/image-information/
---

This guide will take you step by step how to extract information about images in a PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Make sure to set the correct document directory. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the source PDF file

In this step, we will load the source PDF file using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Step 3: Set default resolution

In this step, we will set the default resolution for images. In the example, the default resolution is set to 72.

```csharp
int defaultResolution = 72;
```

## Step 4: Initialize objects and counters

In this step, we will initialize the objects and counters needed to retrieve the image information.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Step 5: Cycle through operators on the first page of the document

In this step, we will walk through the operators on the first page of the document to identify image-related operations.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Step 6: Manage operators and extract image information

In this step, we will manage the different types of operators and extract the information about the images.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

// Handle GSave and GRestore operations for transformations
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Handle the ConcatenateMatrix operation for transformations
else if (opCtm != null)
{
     // Apply the transformation matrix
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Handle the Do operation for images
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Retrieve the image
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Retrieve the dimensions of the image
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calculate the resolution based on the information above
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Display image information
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Sample source code for Image Information using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load the source PDF file
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Define the default resolution for image
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Define array list object which will hold image names
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Insert an object to stack
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Get all the operators on first page of document
foreach (Operator op in doc.Pages[1].Contents)
{
	// Use GSave/GRestore operators to revert the transformations back to previously set
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instantiate ConcatenateMatrix object as it defines current transformation matrix.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Create Do operator which draws objects from resources. It draws Form objects and Image objects
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		// Save previous state and push current state to the top of the stack
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Throw away current state and restore previous one
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Multiply current matrix with the state matrix
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// In case this is an image drawing operator
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Create XImage object to hold images of first pdf page
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Get image dimensions
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Get Height and Width information of image
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Compute resolution based on above information
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Display Dimension and Resolution information of each image
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusion

Congratulation ! You have now learned how to extract image information in a PDF file using Aspose.PDF for .NET. You can use this information for various image processing tasks in your applications.