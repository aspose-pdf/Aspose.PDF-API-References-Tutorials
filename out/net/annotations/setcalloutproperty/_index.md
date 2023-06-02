---
title: Set Callout Property
linktitle: Set Callout Property
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set Callout Property using Aspose.PDF for .NET. Customize annotations with callout lines, text color, and ending styles.
type: docs
weight: 130
url: /content/net/annotations/setcalloutproperty/
---
Aspose.PDF for .NET is a powerful library for creating, manipulating, and converting PDF documents in C#. One of the features provided by this library is the ability to set callout properties for free text annotations in PDF documents. This can be done using the `FreeTextAnnotation` class, which allows you to create annotations with callouts.

In this tutorial, we will guide you through the process of setting callout properties for a free text annotation using Aspose.PDF for .NET in C#. Follow the steps below to get started.

## Install Aspose.PDF for .NET

If you haven't already done so, you will need to [download](https://releases.aspose.com/pdf/net/) and install Aspose.PDF for .NET from the Aspose Releases or via NuGet package manager.

## Create a new PDF document

Create a new PDF document using the `Document` class provided by Aspose.PDF for .NET.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Add a new page to the document

Add a new page to the document using the `Pages` collection of the `Document` class.

```csharp
Page page = doc.Pages.Add();
```

## Set default appearance

Set the default appearance for the free text annotation by creating a new `DefaultAppearance` object and setting its properties such as `TextColor` and `FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Create a free text annotation with callout

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

## Add the free text annotation to the page

Add the free text annotation to the page by using the `Annotations` collection of the `Page` class.

```csharp
page.Annotations.Add(fta);
```

## Add text to the annotation

Add text to the annotation by setting the `RichText` property to a string of formatted XML. In this tutorial, we're setting the text color to red and the font size to 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\"  style=\"color:#FF
```

## 8. save the document

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
