---
title: Resize Images In PDF File
linktitle: Resize Images In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to resize images in PDF file using Aspose.PDF for .NET.
type: docs
weight: 250
url: /ru/net/programming-with-images/resize-images/
---
In this tutorial, we will walk you through how to resize images in PDF file using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## Step 1: Loading the PDF document

To get started, use the following code to load the PDF document:

```csharp
// Initialize the time
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open the document
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Be sure to provide the correct path to your PDF document.

## Step 2: Optimization options initialization

Before resizing the images, we need to initialize the optimization options. Use the following code:

```csharp
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activate the CompressImages option
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Set image quality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Activate the ResizeImages option
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Set maximum resolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

You can adjust the optimization settings according to your needs.

## Step 3: Optimization of the PDF document

Now we are going to optimize the PDF document using the optimization options we defined. Use the following code:

```csharp
// Optimize the PDF document using the OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Save the updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Be sure to provide the desired path and filename for the updated PDF document.

### Sample source code for Resize Images using Aspose.PDF for .NET 
```csharp
// Initialize Time
var time = DateTime.Now.Ticks;
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Set CompressImages option            
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Set ImageQuality option             
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Set ResizeImage option            
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Set MaxResolution option            
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Optimize PDF document using OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You have successfully resized images in a PDF document using Aspose.PDF for .NET. You can now apply this method to your own projects to change the size of images in PDF files.

### FAQ's

#### Q: Why would I want to resize images in a PDF file using Aspose.PDF for .NET?

A: Resizing images in a PDF file can help optimize the document's size and improve its performance. It is especially useful when you want to reduce the file size for easier sharing or faster loading of PDF documents.

#### Q: How does image resizing impact the quality of images in the PDF document?

A: Image resizing involves reducing the dimensions and resolution of images, which can result in a smaller file size. While this can reduce image quality to some extent, the `ImageQuality` parameter (`optimizeOptions.ImageCompressionOptions.ImageQuality`) allows you to control the balance between image size and quality.

#### Q: What is the purpose of the `MaxResolution` option in the optimization settings?

A: The `MaxResolution` option (`optimizeOptions.ImageCompressionOptions.MaxResolution`) sets the maximum resolution for images in the PDF document. Images with higher resolutions will be scaled down to this specified value during the optimization process.

#### Q: How do I adjust the optimization settings for image resizing?

A: In the provided code, you can modify the values of the optimization options to achieve the desired image resizing and compression. For example, you can change the `ImageQuality` and `MaxResolution` values to customize the optimization process according to your requirements.

#### Q: Can I selectively resize specific images within the PDF document?

A: The provided code optimizes all images in the PDF document using the same optimization settings. If you want to selectively resize specific images, you may need to modify the code to target those images individually.

#### Q: How does the `pdfDocument.OptimizeResources` method work in resizing images?

A: The `OptimizeResources` method applies the specified optimization options to the PDF document, including image resizing and compression. It helps reduce the file size of the PDF document by applying the defined optimization settings to its resources.

#### Q: Is it possible to preview the resized images before saving the PDF document?

A: The provided code directly optimizes and saves the PDF document with resized images. If you want to preview the resized images before saving, you may need to modify the code to generate preview images as well.

#### Q: How do I integrate this image resizing method into my own projects?

A: To integrate this method into your projects, follow the outlined steps and modify the code as needed. You can automate the process of resizing images in PDF documents by incorporating this code into your application.

#### Q: Does the Aspose.PDF for .NET library offer any other capabilities for PDF optimization?

A: Yes, the Aspose.PDF for .NET library provides various optimization options beyond image resizing, such as font and text optimization, removing unused objects, and reducing redundant data. You can explore the library's documentation and examples to discover its full range of optimization features.