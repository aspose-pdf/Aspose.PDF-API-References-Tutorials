---
title: Extracting Image
linktitle: Extracting Image
second_title: Aspose.PDF for .NET API Reference
description: Easily extract images from PDF documents with Aspose.PDF for .NET.
type: docs
weight: 70
url: /de/net/programming-with-security-and-signatures/extracting-image/
---
Extracting images from a PDF document can be useful in many cases. With Aspose.PDF for .NET, you can extract images easily using the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here are the necessary import directives:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file from which you want to extract the image. Replace `"YOUR DOCUMENTS DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Step 3: Extract image from PDF document

Now we will extract the image from the PDF document using the following code:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

In this example, we loop through each field of the form in the PDF document. If a signature field is found, we extract the associated image and save it to a JPEG file.

### Sample source code for Extracting Image using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Conclusion

Congratulation ! Now you have a step by step guide to extract images from a PDF document using Aspose.PDF for .NET. You can integrate this code into your own projects to extract images and use them as needed.

Be sure to check out the official Aspose.PDF documentation for more information on advanced image extraction and PDF document manipulation features.


### FAQ's

#### Q: Is Aspose.PDF for .NET suitable for beginners?

A: While some familiarity with C# programming is helpful, our tutorial is designed to be beginner-friendly, guiding you through each step.

#### Q: Can I extract multiple images at once?

A: Absolutely! By implementing loops and adapting the provided code, you can extract multiple images from a single PDF document.

#### Q: Is Aspose.PDF for .NET the only solution for image extraction?

A: While there are other tools available, Aspose.PDF for .NET is renowned for its efficiency and comprehensive features.

#### Q: Can I use the extracted images for commercial purposes?

A: Yes, once extracted, the images are yours to use as needed, including for commercial projects.

#### Q: Where can I find more resources on PDF manipulation with Aspose.PDF?

A: Visit our official documentation for a wealth of resources and insights on advanced PDF manipulation with Aspose.PDF for .NET.