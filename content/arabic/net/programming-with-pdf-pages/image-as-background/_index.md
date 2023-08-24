---
title: Set Image As Page Background In PDF File
linktitle: Set Image As Page Background In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to set an image as a page background in PDF file using Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-pdf-pages/image-as-background/
---
In this tutorial, we'll walk you through the step-by-step process to set an image as a page background using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to add an image as a page background in a PDF document using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited PDF document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Create a new document
Then you can create a new Document object using the `Document` class.

```csharp
Document doc = new Document();
```

## Step 3: Add a new page to the document
Now you can add a new page to the Document object using the `Add()` method of the `Pages` class.

```csharp
Page page = doc.Pages.Add();
```

## Step 4: Create a Background Artifact object
Then you can create a new BackgroundArtifact object to set the background image.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Step 5: Add the background to the page
Then you can add the BackgroundArtifact object to the page's artifact collection using the `Artifacts` property of the `Page` class.

```csharp
page. Artifacts. Add(background);
```

## Step 6: Save the PDF document
Finally, you can save the PDF document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Sample source code for Image As Background using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create a new Document object
Document doc = new Document();
// Add a new page to document object
Page page = doc.Pages.Add();
// Create Background Artifact object
BackgroundArtifact background = new BackgroundArtifact();
// Specify the image for backgroundartifact object
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Add backgroundartifact to artifacts collection of page
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Save the document
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Conclusion
In this tutorial, we learned how to set an image as a page background in a PDF document using Aspose.PDF for .NET. By following this step-by-step guide, you can easily add a background image to your PDF documents. Aspose.PDF offers a powerful and flexible API for working with PDF files, including page background customization. You can now apply this feature in your own projects to create PDF documents with custom background images

### FAQ's for set image as page background in PDF file

#### Q: How can I set an image as a page background in a PDF document using Aspose.PDF for .NET?

A: To set an image as a page background in a PDF document using Aspose.PDF for .NET, you can follow these steps:

1. Set the document directory by specifying the path where you want to save your edited PDF document.
2. Create a new Document object using the `Document` class.
3. Add a new page to the Document object using the `Add()` method of the `Pages` class.
4. Create a new BackgroundArtifact object to set the background image. You can specify the image file using `File.OpenRead()` method.
5. Add the BackgroundArtifact object to the page's artifact collection using the `Artifacts` property of the `Page` class.
6. Save the PDF document to a file using the `Save()` method of the `Document` class, and specify the correct path and file name for the output.

#### Q: Can I add multiple background images to different pages of the PDF document?

A: Yes, you can add multiple background images to different pages of the PDF document by repeating the process described in the tutorial for each page. Simply create a new BackgroundArtifact object with the desired image for each page and add it to the respective page's artifact collection.

#### Q: Can I apply image scaling or positioning to the background image on the page?

A: Yes, you can apply image scaling or positioning to the background image on the page by manipulating the `background.BackgroundImage` property of the BackgroundArtifact object. Before adding the BackgroundArtifact to the page, you can modify the image properties, such as width, height, and position, to customize how the image appears as the background.

#### Q: Does Aspose.PDF for .NET support adding background images to existing PDF documents with content?

A: Yes, Aspose.PDF for .NET allows you to add background images to existing PDF documents with content. You can load an existing PDF document, add the background image to the desired page, and then save the updated document to a new file or overwrite the original file.

#### Q: Can I use images of different formats as the page background, such as PNG or BMP?

A: Yes, you can use images of different formats as the page background, such as PNG or BMP, in addition to the JPEG format used in the tutorial. Aspose.PDF for .NET supports a wide range of image formats, and you can use any supported image format as the background for PDF pages.