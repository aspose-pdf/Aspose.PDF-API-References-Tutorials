---
title: Delete Images
linktitle: Delete Images
second_title: Aspose.PDF for .NET API Reference
description: Easily delete images from a PDF file with Aspose.PDF for .NET.
type: docs
weight: 110
url: /content/net/programming-with-images/delete-images/
---

This guide will take you step by step how to delete images from a PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Step 3: Delete a specific image

In this step, we are going to delete a specific image from a particular page. Use the `Delete` method of the page resource `Images` object to delete the image. In the example below, we delete the image with index 1 from the first page.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Step 4: Save the updated PDF file

Save the updated PDF file using the `Save` method of the `pdfDocument` object. Specify the output path for the PDF file.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Delete Images using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
// Delete a particular image
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Save updated PDF file
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Congratulation ! You have successfully deleted images from a PDF file using Aspose.PDF for .NET. The updated PDF file is saved in the specified directory. You can now use this PDF file without the deleted images.