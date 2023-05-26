---
title: Add Swf File As Annotation
linktitle: Add Swf File As Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add SWF files as annotations in Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 30
url: /net/annotations/addswffileasannotation/
---
If you're a .NET developer looking to add a SWF multimedia file as an annotation to your PDF document using Aspose.PDF for .NET, this step-by-step guide is for you. In this article, we'll explain how to add SWF files as annotations in your PDF documents using the C# programming language. 

Follow the below steps to add an SWF file as an annotation in your PDF document using Aspose.PDF for .NET:

## Step 1: Set the directory path

First, we need to set the directory path where the PDF file and SWF file are stored. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace "YOUR DOCUMENT DIRECTORY" with the path to your document directory.

## Step 2: Load the PDF document

Next, we need to load the PDF document using the following code:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

This code will load the "AddSwfFileAsAnnotation.pdf" file from the document directory.

## Step 3: Get the page to add annotation

Now, we need to get the reference of the page to which we want to add the annotation. In this tutorial, we'll add the annotation to the first page of the document.

```csharp
Page page = doc.Pages[1];
```

## Step 4: Create a ScreenAnnotation object

We can now create a `ScreenAnnotation` object with the SWF file as an argument.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

The `ScreenAnnotation` constructor takes three arguments:

- `page`: The page to which the annotation will be added.
- `rectangle`: The rectangle in which the SWF file will be displayed on the page.
- `dataDir + "input.swf"`: The path to the SWF file.

## Step 5: Add the annotation to the page

Now, we can add the annotation to the annotations collection of the page.

```csharp
page.Annotations.Add(annotation);
```

## Step 6: Save the updated PDF document

Finally, we need to save the updated PDF document with the annotation using the following code:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

This code will save the updated PDF document with the annotation as "AddSwfFileAsAnnotation_out.pdf" in the document directory.

### Example source code for Adding SWF file as an annotation using Aspose.PDF for .NET

```csharp
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Open the PDF document
	Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

	// Get reference of the page to which you need to add the annotation
	Page page = doc.Pages[1];

	// Create ScreenAnnotation object with .swf multimedia file as an argument
	ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

	// Add the annotation to annotations collection of page
	page.Annotations.Add(annotation);

	dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
	// Save the update PDF document with annotation
	doc.Save(dataDir);
```        

