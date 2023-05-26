---
title: Set Properties For Print Dialog
linktitle: Set Properties For Print Dialog
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set properties for print dialog in Aspose.PDF for .NET using step-by-step guide.
type: docs
weight: 320
url: /net/programming-with-document/setpropertiesforprintdialog/
---
here's a step-by-step guide for setting properties for the print dialog using Aspose.PDF for .NET:


## Step 1: Define the directory where your PDF document is located:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
## Step 2: Create a new instance of the `Document` class:

```csharp
using (Document doc = new Document())
{
  // Code here
}
```
   
## Step 3: Add a new page to the document:

```csharp
doc.Pages.Add();
```
   
## Step 4: Set the duplex property to `DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Step 5: Save the document with the specified file name and format:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

## Conclusion

Aspose.PDF for .NET makes it easy to set properties for the print dialog in your PDF files. By following the step-by-step guide above, you can quickly optimize your PDF files for printing.

### Example source code for Set Properties For Print Dialog using Aspose.PDF for .NET

```csharp

	var dataDir = "YOUR DOCUMENT DIRECTORY";

	using (Document doc = new Document())
	{
		doc.Pages.Add();
		doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
		doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
	}

```

