---
title: Add Image In PDF File
linktitle: Add Image In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily add an image in PDF file using Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-images/add-image/
---
This guide will take you step by step how to add an image in PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Step 3: Set Image Coordinates

Set the coordinates of the image you want to add. The variables `lowerLeftX`, `lowerLeftY`, `upperRightX` and `upperRightY` represent the coordinates of the lower left corner and the upper right corner of the image respectively.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Step 4: Get the page where the image should be added

To add the image to a specific page of the PDF document, we first need to retrieve that page. In this example, we add the image to the second page (index 1) of the document.

```csharp
Page page = pdfDocument.Pages[1];
```

## Step 5: Load the image from a stream

We will now load the image we want to add to the PDF document. This example assumes you have an image file named `aspose-logo.jpg` in the same directory as your document. Replace the file name if necessary.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Step 6: Add the Image to Page Assets

To use the image in the PDF document, we need to add it to the page's resource image collection.

```csharp
page.Resources.Images.Add(imageStream);
```

## Step 7: Save current graphics state

Before drawing the image, we need to save the current graphics state using the `GSave` operator. This ensures that changes to the graphics state can be rolled back later.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Step 8: Create Rectangle and Matrix objects

We will now create a `Rectangle` object and a `Matrix` object. The rectangle represents the position and size of the image, while the matrix defines how the image should be placed.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Step 9: Concatenate matrix for image placement

To specify how the image should be placed in the rectangle, we use the `ConcatenateMatrix` operator. This operator defines the transformation matrix that maps the coordinate space of the image to the coordinate space of the page.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Step 10: Draw the image

In this step we will draw the image on the page using the `Do` operator. The `Do` operator takes the image name from the resources and draws it onto the page.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Step 11: Restore graphics state

After drawing the image, we need to restore the previous graphics state using the `GRestore` operator.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Step 12: Save the updated document

Finally, we'll save the updated document to a new file. Update the `dataDir` variable with the desired output directory and filename.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Add Image using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Set coordinates
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Get the page where image needs to be added
Page page = pdfDocument.Pages[1];
// Load image into stream
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Add image to Images collection of Page Resources
page.Resources.Images.Add(imageStream);
// Using GSave operator: this operator saves current graphics state
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Create Rectangle and Matrix objects
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Using ConcatenateMatrix (concatenate matrix) operator: defines how image must be placed
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Using Do operator: this operator draws image
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Using GRestore operator: this operator restores graphics state
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Conclusion

In this tutorial, we learned how to add an image to a PDF document using Aspose.PDF for .NET. We've covered every step in detail, from opening the document to saving the updated version. By following this guide, you should now be able to embed images into your PDF files programmatically using C# and Aspose.PDF.

### FAQ's for add image in PDF file

#### Q: Why would I want to add an image to a PDF document?

A: Adding images to a PDF document can enhance visual content, provide additional context, or include logos and graphics in your PDF files.

#### Q: Can I add images to specific pages within a PDF document?

A: Yes, you can specify the page where you want to add the image. In the provided code, the image is added to the second page of the PDF document.

#### Q: How do I adjust the position and size of the added image?

A: You can modify the `lowerLeftX`, `lowerLeftY`, `upperRightX`, and `upperRightY` variables in the code to set the coordinates of the image and control its size and position on the page.

#### Q: What type of image formats can I add using this method?

A: The provided code example assumes you are loading a JPG image (`aspose-logo.jpg`). Aspose.PDF for .NET supports various image formats, including PNG, BMP, GIF, and more.

#### Q: How do I ensure that the added image fits within the specified coordinates?

A: Make sure to adjust the coordinates and size of the `Rectangle` object (`rectangle`) to match the dimensions of the image and its desired placement on the page.

#### Q: Can I add multiple images to a single PDF page?

A: Yes, you can add multiple images to a single PDF page by repeating the process for each image and adjusting the coordinates and other parameters accordingly.

#### Q: How does the `GSave` and `GRestore` operator work in the code?

A: The `GSave` operator saves the current graphics state, allowing you to make changes without affecting the overall graphics context. The `GRestore` operator restores the previous graphics state after changes are made.

#### Q: What happens if the image file is not found at the specified path?

A: If the image file is not found at the specified path, the code will throw an exception when trying to load the image stream. Make sure the image file is located in the correct directory.

#### Q: Can I customize the image placement and appearance further?

A: Yes, you can customize the image appearance by modifying the `Matrix` object and adjusting other operators within the code. Refer to the Aspose.PDF documentation for advanced customization.

#### Q: How can I test if the image was successfully added to the PDF?

A: After applying the provided code to add the image, open the modified PDF file and verify that the image is displayed on the specified page with the correct placement.

#### Q: Does adding images affect the original content of the PDF document?

A: Adding images does not affect the original content of the PDF document. It enhances the document by including visual elements.