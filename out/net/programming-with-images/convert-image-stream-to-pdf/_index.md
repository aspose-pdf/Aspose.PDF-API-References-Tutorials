---
title: Convert Image Stream to PDF
linktitle: Convert Image Stream to PDF
second_title: Aspose.PDF for .NET API Reference
description: Easily convert an image stream to a PDF file with Aspose.PDF for .NET.
type: docs
weight: 70
url: /content/net/programming-with-images/convert-image-stream-to-pdf/
---

This guide will take you step by step how to convert an image stream to a PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your image is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Instantiate a Document object

In this step, we will instantiate a `Document` object using the empty constructor of the `Aspose.Pdf.Document` class.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Step 3: Add a page to the PDF document

Add a page to the PDF document using the `Add` method of the `Pages` object of `pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Step 4: Read the image stream

In this step we will create a `FileStream` object to read the image file from the stream.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Step 5: Read the image into a byte array

Read the image from the stream and store it in a byte array using the `Read` method of the `fs` object.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Step 6: Create a MemoryStream object from the byte array

Create a `MemoryStream` object from the byte array containing the image.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Step 7: Create an Image Object

In this step, we will create an `Image` object using the `Aspose.Pdf.Image` class. Specify the stream of the image using the `ImageStream` property and pass the `ms` object we created earlier.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Step 8: Add the Image object to the Paragraphs collection

Add the `imageht` object to the `Paragraphs` collection of the `sec` section.

```csharp
sec.Paragraphs.Add(imageht);
```

## Step 9: Save the PDF document

Save the PDF document using the `Save` method of the `pdf1` object. Specify the output path of the PDF file.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Step 10: Close the MemoryStream object

Close the `ms` object using the `Close` method to release the resources.

```csharp
ms. Close();
```

### Sample source code for Convert Image Stream to PDF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document instance by calling its empty constructor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Add a Page into the pdf document
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Create a FileStream object to read the imag file
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Read the image into Byte array
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Create a MemoryStream object from image Byte array
MemoryStream ms = new MemoryStream(data);
// Create an image object
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Specify the image source as MemoryStream
imageht.ImageStream = ms;
// Add image object into the Paragraphs collection of the section
sec.Paragraphs.Add(imageht);
// Save the Pdf
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Close the MemoryStream Object
ms.Close();
```

## Conclusion

Congratulation ! You have successfully converted an image stream to a PDF file using Aspose.PDF for .NET. The generated PDF file is saved in the specified directory. You can now use this PDF file in your projects or applications.