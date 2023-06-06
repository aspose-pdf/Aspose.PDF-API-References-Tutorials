---
title: PCL to PDF
linktitle: PCL to PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PCL to PDF using Aspose.PDF for .NET.
type: docs
weight: 90
url: /net/document-conversion/pcl-to-pdf/
---

In this tutorial, we will walk you through the process of converting a PCL file to PDF using Aspose.PDF for .NET. PCL (Printer Control Language) is a page description language used primarily for printing on laser printers. By following the steps below, you will be able to convert PCL files to PDF format.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading the PCL file
In this step we will load the PCL file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate the LoadOption object using the PCL load option
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.PclLoadOptions();

// Create the Document object
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "hidetext.pcl", loadopt);
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PCL file is located.

## Step 2: PCL to PDF conversion
After loading the PCL file, we can proceed with the conversion to PDF. Use the following code:

```csharp
// Save the resulting PDF document
doc.Save(dataDir + "PCLToPDF_out.pdf");
```

The code above converts the PCL file to PDF format and saves it as the filename `"PCLToPDF_out.pdf"`.

### Example source code for PCL to PDF using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instantiate LoadOption object using PCL load option
	Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.PclLoadOptions();

	// Create Document object
	Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "hidetext.pcl", loadopt);

	// Save the resultant PDF document
	doc.Save(dataDir + "PCLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PCL file to PDF using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert PCL files to PDF format. This feature can be useful when you have PCL files from laser printers and want to convert them to PDF format.
