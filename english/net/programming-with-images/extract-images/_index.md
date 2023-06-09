---
title: Extract Images
linktitle: Extract Images
second_title: Aspose.PDF for .NET API Reference
description: Easily extract images from a PDF file with Aspose.PDF for .NET.
type: docs
weight: 120
url: /net/programming-with-images/extract-images/
---

This guide will take you step by step how to extract images from a PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Step 3: Extract a specific image

In this step, we are going to extract a specific image from a particular page. Use the `Images` collection of the page`s `Resources` object to access the desired image. In the example below, we extract the image with index 1 from the first page.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Step 4: Save the extracted image

Save the extracted image to a file using the `Save` method of the `xImage` object. Specify the output path and image format (in this example we are using JPEG format).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Step 5: Save the updated PDF file

Save the updated PDF file using the `Save` method of the `pdfDocument` object. Specify the output path for the PDF file.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Extract Images using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extract a particular image
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Save output image
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Save updated PDF file
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Congratulation ! You have successfully extracted images from a PDF using Aspose.PDF for .NET. The extracted image is saved in the specified directory and the updated PDF file is also saved. You can now use these files for your specific needs.
