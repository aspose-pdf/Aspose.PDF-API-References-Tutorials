---
title: Bradley Algorithm
linktitle: Bradley Algorithm
second_title: Aspose.PDF for .NET API Reference
description: Convert a PDF document using the Bradley algorithm with Aspose.PDF for .NET.
type: docs
weight: 30
url: /content/net/programming-with-images/bradley-algorithm/
---

This step-by-step guide explains how to use the Bradley Algorithm with Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Step 3: Define output files

Define the output filenames for the resulting image and the binary image. Replace `"resultant_out.tif"` and `"37116-bin_out.tif"` with the desired names for the output files.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Step 4: Create the Resolution object

Create a `Resolution` object to set the resolution of the TIFF image. In this example, we are using a resolution of 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Step 5: Create the TiffSettings object

Create a `TiffSettings` object to specify settings for the output TIFF file. In this example, we are using LZW compression and a color depth of 1 bit per pixel (1 bpp format).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Step 6: Create the TIFF device

Create a TIFF device using the `TiffDevice` object, specifying the resolution and TIFF settings.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Step 7: Convert the specific page and save the image

Use the `Process` method of the TIFF device to convert a specific page of the PDF document and save the image to a TIFF file. Specify the file output path.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Step 8: Binarize the image using the Bradley algorithm

Use the `BinarizeBradley` method of the TIFF device to binarize the image using the Bradley algorithm. This method takes an input stream of the original image and an output stream for the binary image. Specify the binarization threshold (0.1 in this example).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Sample source code for Bradley Algorithm using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Create Resolution object
Resolution resolution = new Resolution(300);
// Create TiffSettings object
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Create TIFF device
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Convert a particular page and save the image to stream
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Conclusion

Congratulation ! You have successfully completed the conversion using the Bradley algorithm with Aspose.PDF for .NET. You can now use the resulting images in your projects or applications.