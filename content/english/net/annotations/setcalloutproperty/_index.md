---
title: Set Callout Property In PDF File
linktitle: Set Callout Property In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set the callout property in a PDF file using Aspose.PDF for .NET in this detailed, step-by-step tutorial.
type: docs
weight: 130
url: /net/annotations/setcalloutproperty/
---
## Introduction

Creating professional and visually appealing PDF documents often requires the addition of annotations that draw attention to specific content. One such annotation is the callout, which is like those speech bubbles you see in comics. They help clarify or emphasize text within your PDF. Aspose.PDF for .NET makes it incredibly easy to add such annotations to your documents, and in this tutorial, we'll walk through how to set the callout property in a PDF file using this powerful library. Whether you’re a seasoned developer or just starting out, by the end of this guide, you’ll have a clear understanding of how to work with callouts in PDF files.

## Prerequisites

Before we dive into the code, let’s cover the essentials you need to get started.

1. Aspose.PDF for .NET: Make sure you have the Aspose.PDF for .NET library installed. You can download it from [here](https://releases.aspose.com/pdf/net/).
2. IDE: A development environment such as Visual Studio.
3. .NET Framework: Ensure that you have .NET installed on your machine.
4. Temporary License: If you want to try out the full features of Aspose.PDF without limitations, get a [temporary license](https://purchase.aspose.com/temporary-license/).

## Import Packages

Before you begin writing the code, you need to import the necessary packages that will allow you to work with PDF files and annotations.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

These imports will provide you with all the necessary classes and methods to manipulate PDF documents and create annotations like the callout.

## Step 1: Initialize the PDF Document

The first step in our journey is to initialize a new PDF document where we will add our callout annotation. Think of this as setting up a blank canvas where you can start adding elements.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialize a new PDF document
Document doc = new Document();
```
Here, we’re creating a new `Document` object which will serve as our PDF file. The `dataDir` variable is set to the directory where you want to save your PDF file after we’re done.

## Step 2: Add a New Page to the Document

A PDF document can have multiple pages, and in this step, we’ll add a new page to our document. This page will be where our callout annotation will be placed.

```csharp
// Add a new page to the document
Page page = doc.Pages.Add();
```
The `Pages.Add()` method is used to add a new page to the `doc` object. The new page is stored in the `page` variable, which we’ll use later when adding the annotation.

## Step 3: Define the Default Appearance

Annotations, like the callout, have a visual appearance that you can customize. In this step, we’ll define how the text within the callout should look.

```csharp
// Define the default appearance for the annotation
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
We create a `DefaultAppearance` object that defines the text color and font size. Here, the text will be red, and the font size is set to 10. This appearance will be applied to the callout annotation.

## Step 4: Create the Free Text Annotation

Now it’s time to create the actual annotation. The free text annotation is what allows us to add a callout with specific text and styling.

```csharp
// Create a FreeTextAnnotation with a callout
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
We create a `FreeTextAnnotation` object with specific coordinates, defining its position on the page. The `Intent` is set to `FreeTextCallout`, indicating that this is a callout annotation. The `EndingStyle` is set to `OpenArrow`, meaning the callout line will end with an open arrow.

## Step 5: Define the Callout Line Points

A callout annotation has a line that points to the area of interest. Here, we’ll define the points that make up this line.

```csharp
// Define the points for the callout line
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
The `Callout` property is an array of `Point` objects, each representing a coordinate on the page. These points define the path of the callout line, giving it the classic speech-bubble appearance.

## Step 6: Add the Annotation to the Page

After creating and configuring our annotation, the next step is to add it to the page.

```csharp
// Add the annotation to the page
page.Annotations.Add(fta);
```
The `Annotations.Add()` method is used to place the annotation on the page we created earlier. This step effectively "draws" the callout on the PDF page.

## Step 7: Set the Rich Text Content

Callout annotations can include rich text, allowing for formatted content within the bubble. Let’s add some sample text.

```csharp
// Set the rich text for the annotation
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\"  style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">This is a sample</span></p></body>";
```
The `RichText` property is set with HTML content. This allows for detailed formatting within the callout, such as specifying font size, color, and style.

## Step 8: Save the PDF Document

Finally, after setting up everything, we need to save the document. This step finalizes the creation of the PDF with the callout annotation.

```csharp
// Save the document
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
The `Save()` method saves the document to the specified directory with the filename "SetCalloutProperty.pdf". This step concludes our PDF creation process.

## Conclusion

And there you have it! You've just created a PDF document with a callout annotation using Aspose.PDF for .NET. This annotation can be incredibly useful for highlighting or explaining specific parts of your document. Aspose.PDF offers a powerful API that makes PDF manipulation straightforward and flexible. Whether you're adding annotations, converting documents, or handling complex PDF tasks, Aspose.PDF has got you covered.

## FAQ's

### Can I customize the appearance of the callout further?

Absolutely! You can customize various aspects like line color, thickness, and the text’s font family and style.

### Is it possible to add multiple callouts on a single page?

Yes, you can add as many callouts as needed by repeating the steps for each annotation.

### How do I change the position of the callout?

Simply modify the coordinates in the `Rectangle` and `Callout` properties to reposition the annotation.

### Can I add other types of annotations using Aspose.PDF?

Yes, Aspose.PDF supports various annotation types, including highlights, stamps, and file attachments.

### Is the rich text content limited to HTML?

The `RichText` property supports a subset of HTML, allowing you to include styled text and basic formatting.
