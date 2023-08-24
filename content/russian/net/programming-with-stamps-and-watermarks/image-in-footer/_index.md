---
title: Image In Footer
linktitle: Image In Footer
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add an image in the footer section of a PDF document with Aspose.PDF for .NET.
type: docs
weight: 130
url: /ru/net/programming-with-stamps-and-watermarks/image-in-footer/
---
In this tutorial, we will guide you step by step on how to add an image in the footer section of a PDF document using Aspose.PDF for .NET. We will use the provided C# source code to open an existing PDF document, create an image buffer, set its properties, and add it to all pages of the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the existing PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the existing PDF document
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Creating and adding the image in the footer section

Now that the PDF document is loaded, we can create an image stamp and add it to all the pages of the document. Here's how:

```csharp
// Create the frame buffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Set image buffer properties
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Add image buffer to all pages
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

The code above creates an image buffer from the "aspose-logo.jpg" file and sets its properties, such as bottom margin, horizontal and vertical alignment. Then the image buffer is added to all pages of the PDF document.

## Step 4: Saving the modified PDF document

Once the image is added to the footer section, we can save the modified PDF document. Here's how:

```csharp
// Save the modified PDF document
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Image In Footer using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Create footer
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Set properties of the stamp
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Add footer on all pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Save updated PDF file
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You have learned how to add an image in the footer section of a PDF document using Aspose.PDF for .NET. You can now customize the footers of your PDF documents by adding images.

### FAQ's for image in footer

#### Q: What is the purpose of adding an image to the footer section of a PDF document?

A: Adding an image to the footer section of a PDF document allows you to include visual elements, such as a logo or watermark, at the bottom of every page. This can enhance the branding and aesthetics of the PDF content.

#### Q: How does the provided C# source code achieve adding an image to the footer section of a PDF document?

A: The provided code demonstrates how to load an existing PDF document, create an `ImageStamp` object from an image file, set properties such as bottom margin and alignment, and then add the image stamp to the footer of all pages.

#### Q: Can I adjust the position and alignment of the image within the footer section?

A: Yes, you can adjust the position and alignment of the image within the footer section by modifying the properties of the `ImageStamp` object. The code snippet sets properties such as `BottomMargin`, `HorizontalAlignment`, and `VerticalAlignment`.

#### Q: Is it possible to add different images to the footer section on different pages of the PDF document?

A: Yes, you can add different images to the footer section on different pages by creating separate `ImageStamp` objects with different image files and properties, and then adding them to specific pages.

#### Q: How does the code ensure that the image is added to all pages of the PDF document?

A: The provided code uses a `foreach` loop to iterate through all pages of the PDF document and adds the same `ImageStamp` to each page's footer section.

#### Q: Can I add other elements, such as text or shapes, to the footer section using a similar approach?

A: Yes, you can add other elements like text or shapes to the footer section using a similar approach by creating the appropriate stamp objects (e.g., `TextStamp`) and setting their properties accordingly.

#### Q: How do I specify the path to the image file that I want to add to the footer?

A: The path to the image file is specified when creating the `ImageStamp` object, as shown in the code. Make sure to provide the correct path to the image file.

#### Q: Can I customize the image's size within the footer section?

A: Yes, you can customize the image's size within the footer section by adjusting the dimensions of the `ImageStamp` using properties like `Width` and `Height`.

#### Q: Is it possible to remove or replace the image in the footer section after it has been added?

A: Yes, you can remove or replace the image in the footer section by modifying the contents of the `ImageStamp` object or removing the stamp from specific pages.

#### Q: How does the code handle scenarios where the image's dimensions exceed the available space in the footer?

A: The code sets properties such as `BottomMargin`, `HorizontalAlignment`, and `VerticalAlignment` to control the positioning and alignment of the image. Ensure that these properties are adjusted to prevent any overlap or layout issues.