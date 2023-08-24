---
title: Page Orientation According Image Dimensions
linktitle: Page Orientation According Image Dimensions
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to set page orientation based on image dimensions with Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/document-conversion/page-orientation-according-image-dimensions/
---
In this tutorial, we'll walk you through the process of setting page orientation based on an image's dimensions using Aspose.PDF for .NET. We will loop through a list of JPG images in a given directory and automatically adjust the page orientation based on the width of each image. Follow the steps below to achieve this.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Browse JPG images
At this step, we will browse all JPG images in a given directory. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a new PDF document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Retrieve the names of all JPG files in a particular directory
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your JPG images are located.

## Step 2: Creation of the page and the image
After browsing the JPG files, we will create a page and an image for each file. Use the following code:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Create a Page object
Aspose.Pdf.Page page = doc.Pages.Add();

// Create an Image object
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Step 3: Checking image dimensions
Now let's check the dimensions of each image to determine the page orientation. Use the following code:

```csharp
// Create a BitMap object to get information from the image file
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Check if the width of the image is greater than the width of the page or not
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// If the width of the image is less than the width of the page, set the orientation of the page to portrait
page.PageInfo.IsLandscape = false;
```

## Step 4: Adding the image to the PDF document
After checking the dimensions of the image, we will add the image to the PDF document's paragraph collection. Use the following code:

```csharp
// Add the image to the paragraph collection of the PDF document
page.Paragraphs.Add(image1);
```

## Step 5: Saving the PDF file
Once we have added all the images to the PDF document, we can now save the resulting PDF file. Here is the last step:

```csharp
// Save the PDF file
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the desired directory where you want to save the output PDF file.

### Example source code for Page Orientation According Image Dimensions using Aspose.PDF for .NET

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Retrieve names of all the JPG files in a particular Directory
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Create a page object
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Creat an image object
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Create a BitMap object in order to get the information of image file
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Check if the width of the image file is greater than Page width or not
	if (myimage.Width > page.PageInfo.Width)
		// If the Image width is greater than page width, then set the page orientation to Landscape
		page.PageInfo.IsLandscape = true;
	else
		// If the Image width is less than page width, then set the page orientation to Portrait
		page.PageInfo.IsLandscape = false;
	// Add the image to paragraphs collection of the PDF document 
	page.Paragraphs.Add(image1);
}
// Save the Pdf file
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Conclusion
In this tutorial, we've covered the step-by-step process of setting page orientation based on an image's dimensions using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to create a PDF document with the correct page orientation for each image. This feature is useful when you have images of different sizes and want to embed them into a PDF document.

### FAQ's

#### Q: Can I use other image formats instead of JPG for setting page orientation based on image dimensions?

A: Yes, you can use other image formats such as PNG, BMP, or GIF in addition to JPG for setting page orientation based on image dimensions. The provided code loops through all image files with the ".JPG" extension, but you can modify it to include other image formats as well.

#### Q: What happens if an image's dimensions are exactly equal to the page width?

A: If an image's width is exactly equal to the page width, the page orientation will be set to portrait. In the code provided, the page orientation is set to landscape only if the image's width is greater than the page width.

#### Q: Can I customize the page orientation logic based on specific requirements?

A: Yes, you can customize the page orientation logic based on specific requirements. For example, you can set a threshold value to determine when the page orientation should be set to landscape or portrait. Additionally, you can consider factors such as image height or aspect ratio to determine the page orientation.

#### Q: Can I add other content, such as text or tables, to the PDF document along with the images?

A: Yes, you can add other content, such as text or tables, to the PDF document along with the images. Aspose.PDF for .NET provides a rich set of features to manipulate PDF documents, including adding text, images, tables, and other elements to the pages.