---
title: Set Callout Property In PDF File
linktitle: Set Callout Property In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set Callout Property in PDF File using Aspose.PDF for .NET. Customize annotations with callout lines, text color, and ending styles.
type: docs
weight: 130
url: /ar/net/annotations/setcalloutproperty/
---
Aspose.PDF for .NET is a powerful library for creating, manipulating, and converting PDF documents in C#. One of the features provided by this library is the ability to set callout properties for free text annotations in PDF documents. This can be done using the `FreeTextAnnotation` class, which allows you to create annotations with callouts.

In this tutorial, we will guide you through the process of setting callout properties for a free text annotation using Aspose.PDF for .NET in C#. Follow the steps below to get started.

## Install Aspose.PDF for .NET

If you haven't already done so, you will need to [download](https://releases.aspose.com/pdf/net/) and install Aspose.PDF for .NET from the Aspose Releases or via NuGet package manager.

## Step 1: Create a new PDF document

Create a new PDF document using the `Document` class provided by Aspose.PDF for .NET.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Step 2: Add a new page to the document

Add a new page to the document using the `Pages` collection of the `Document` class.

```csharp
Page page = doc.Pages.Add();
```

## Step 3: Set default appearance

Set the default appearance for the free text annotation by creating a new `DefaultAppearance` object and setting its properties such as `TextColor` and `FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Step 4: Create a free text annotation with callout

Create a new free text annotation with callout by using the `FreeTextAnnotation` class. Set the `Intent` property to `FreeTextIntent.FreeTextCallout` to specify that this is a callout annotation. Set the `EndingStyle` property to `LineEnding.OpenArrow` to specify the style of the arrow at the end of the callout. Set the `Callout` property to an array of `Point` objects that represent the points on the page where the callout line should be drawn.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Step 5: Add the free text annotation to the page

Add the free text annotation to the page by using the `Annotations` collection of the `Page` class.

```csharp
page.Annotations.Add(fta);
```

## Step 6: Add text to the annotation

Add text to the annotation by setting the `RichText` property to a string of formatted XML. In this tutorial, we're setting the text color to red and the font size to 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\"  style=\"color:#FF
```

## Step 7: save the document

Now save the document by using the following code:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Example source code for Set Callout Property using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\"  style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">This is a sample</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Conclusion

In this tutorial, we explored how to set callout properties for a free text annotation in a PDF document using Aspose.PDF for .NET. Callout annotations are useful for providing additional information or explanations related to specific areas in a document. Aspose.PDF for .NET provides a wide range of features and capabilities to work with PDF files, including creating and customizing annotations, such as callouts. By following the step-by-step guide and using the provided C# source code, developers can easily implement callout annotations in their PDF documents, enhancing the usability and clarity of their documents. Aspose.PDF for .NET is a versatile and reliable library for PDF operations in .NET applications, offering powerful tools to handle various PDF-related tasks efficiently.

### FAQ's for set callout property in PDF file

#### Q: What is a callout annotation in a PDF document?

A: A callout annotation in a PDF document is a type of annotation that allows you to create a text box with a leader line pointing to a specific area in the document. It is commonly used to provide additional information or comments related to a particular section or element in the document.

#### Q: Can I customize the appearance of the callout annotation using Aspose.PDF for .NET?

A: Yes, you can customize various properties of the callout annotation, such as the color, font size, text alignment, line style, arrow style, and more.

#### Q: How do I add text to the callout annotation?

A: To add text to the callout annotation, you can set the `RichText` property of the `FreeTextAnnotation` object. The `RichText` property takes a string of formatted XML that represents the text to be displayed in the callout annotation.

#### Q: Can I add multiple callout annotations to a PDF document using Aspose.PDF for .NET?

A: Yes, you can create multiple callout annotations in a PDF document by creating multiple instances of the `FreeTextAnnotation` object and adding them to different pages or locations in the document.