---
title: Hide Page Numbers In TOC
linktitle: Hide Page Numbers In TOC
second_title: Aspose.PDF for .NET API Reference
description: Learn how to hide page numbers in a table of contents using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 220
url: /fr/net/programming-with-document/hidepagenumbersintoc/
---
In this article, we will discuss the implementation of the Hide Page Numbers In TOC feature of Aspose.PDF for .NET using C#. We will start with a brief introduction to Aspose.PDF for .NET and then dive into the step-by-step guide to implement this feature. 

## Introduction to Aspose.PDF for .NET

Aspose.PDF for .NET is a powerful PDF manipulation component that allows developers to create, edit, and manipulate PDF files programmatically. It provides a wide range of features and functionalities that make it easy to work with PDF documents. Aspose.PDF for .NET supports both 32-bit and 64-bit operating systems and can be used with .NET Framework, .NET Core, and Xamarin platforms. 

## What is Hide Page Numbers In TOC feature?

Table Of Contents (TOC) is an essential part of a PDF document that provides users with a quick overview of the content. Sometimes, users may want to hide page numbers in the TOC to make it more user-friendly. Aspose.PDF for .NET provides a built-in feature to hide page numbers in the TOC. This feature can be used to create more user-friendly PDF documents. 

## Prerequisites

To follow this tutorial, you will need the following:

- Visual Studio 2010 or later
- Aspose.PDF for .NET installed on your system
- Basic knowledge of C# programming language

## Step-by-step guide to implement Hide Page Numbers In TOC feature

Follow the steps below to implement the Hide Page Numbers In TOC feature using Aspose.PDF for .NET:

## Step 1: Create a new C# console application in Visual Studio

Open Visual Studio and create a new C# console application.

## Step 2: Add reference to Aspose.PDF for .NET

Right-click on the References folder in your project and select Add Reference. Browse to the location where Aspose.PDF for .NET is installed on your system and add a reference to it.

## Step 1: Create a new PDF document

Create a new PDF document using the following code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Step 2: Create a TOC page

Create a new page for the TOC and add it to the PDF document using the following code:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Step 3: Add list section to the sections collection of PDF document

Add the list section to the sections collection of the PDF document using the following code:

```csharp
tocPage.TocInfo = tocInfo;
```

## Step 4: Define the format of the four levels list

Define the format of the four levels list by setting the left margins and text format settings of each level using the following code:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Step 5: Add four headings in the section

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Example Source Code for Hide Page Numbers In TOC using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Add the list section to the sections collection of the Pdf document
tocPage.TocInfo = tocInfo;
//Define the format of the four levels list by setting the left margins and
//text format settings of each level

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Add four headings in the section
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Conclusion

In this tutorial, we explored how to work with XMP metadata in a PDF document using Aspose.PDF for .NET. XMP metadata provides valuable information about the PDF document, including its title, author, creation date, and more. Aspose.PDF for .NET allows developers to access and manipulate this metadata, providing a flexible and powerful API for working with PDF documents.

### FAQ's

#### Q: What is XMP metadata in a PDF document?

A: XMP (Extensible Metadata Platform) metadata in a PDF document is a standard format for storing metadata information about the document. It includes details such as document title, author, creation date, keywords, and more. XMP metadata provides a structured and standardized way to store and share information about the PDF document.

#### Q: Can I modify the XMP metadata of a PDF document using Aspose.PDF for .NET?

A: Yes, you can modify the XMP metadata of a PDF document programmatically using Aspose.PDF for .NET. You can access the `Info` property of the `Document` object, which gives you access to the XMP metadata properties. You can then update the values of these properties to modify the XMP metadata of the PDF document.

#### Q: Can I extract custom XMP metadata properties from a PDF document using Aspose.PDF for .NET?

A: Yes, you can extract custom XMP metadata properties from a PDF document using Aspose.PDF for .NET. You can use the `Metadata` property of the `Document` object, which provides access to all the XMP metadata properties of the PDF document. You can then extract custom properties and use their values as needed.