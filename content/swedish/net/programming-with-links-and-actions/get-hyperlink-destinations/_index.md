---
title: Get Hyperlink Destinations In PDF File
linktitle: Get Hyperlink Destinations In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract hyperlink destinations in PDF file using Aspose.PDF for .NET.
type: docs
weight: 60
url: /sv/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET is a powerful library for manipulating and extracting information in PDF file using the C# programming language. In this tutorial, we will focus on extracting hyperlink destinations from a PDF file using Aspose.PDF for .NET.

## Prerequisites

Before you begin, make sure you have the following:

- An integrated development environment (IDE) such as Visual Studio.
- The Aspose.PDF library for .NET installed on your machine.

## Step 1: Setting up the development environment

Before you start writing code, you need to set up your development environment by creating a new C# project in your favorite IDE.

## Step 2: Import Aspose.PDF references

To use Aspose.PDF for .NET, you need to add the appropriate references to your project. Follow the steps below to import the necessary references:

1. In your project, right-click "References" and select "Add Reference".
2. In the "Add Reference" window, locate and select the DLL files of Aspose.PDF for .NET.
3. Click "OK" to import the references into your project.

## Step 3: Loading the PDF File

Before you can extract hyperlink destinations, you must load the PDF file into your application. Use the following code to load the PDF file:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load the PDF file
Document document = new Document(dataDir + "input.pdf");
```

Be sure to specify the correct path to your document directory and the PDF file you want to process.

## Step 4: Navigating the pages of the document

Now that the PDF file is loaded, you need to go through all the pages of the document. This will allow you to get

ir the hyperlink annotations present on each page. Use the following code to iterate through the pages of the document:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Get the link annotations of a specific page
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Create a list to store all the links
     IList<Annotation> list = selector. Selected;
     // Loop through each item in the list
     foreach(LinkAnnotation a in list)
     {
         // Print destination URL
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

This code loops through each page of the document and selects the hyperlink annotations present on each page. Then it stores these annotations in a list and prints the destination URL for each link.

## Step 5: Obtaining Hyperlink Destinations

The last step is to extract the hyperlink destinations from the hyperlink annotations. The following code shows you how to do it:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Use the destination as you wish
     }
}
```

In this code, we get each hyperlink destination from the link annotations and store the destination in a variable. You can then use this destination as you wish in your application.

### Sample source code for Get Hyperlink Destinations using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the PDF file
	Document document = new Document(dataDir + "input.pdf");
	// Traverse through all the page of PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Get the link annotations from particular page
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Create list holding all the links
		IList<Annotation> list = selector.Selected;
		// Iterate through invidiaul item inside list
		foreach (LinkAnnotation a in list)
		{
			// Print the destination URL
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### FAQs for get hyperlink destinations in PDF file

#### Q: What is a hyperlink destination in a PDF file?

A: A hyperlink destination in a PDF file is a specific location or target that a hyperlink points to. It could be a URL, a page within the same document, or an external document.

#### Q: How can extracting hyperlink destinations benefit my PDF document analysis?

A: Extracting hyperlink destinations allows you to identify and catalog all the targets that hyperlinks point to within a PDF document. This information can be useful for content validation, link verification, and data analysis.

#### Q: How does Aspose.PDF for .NET assist in extracting hyperlink destinations?

A: Aspose.PDF for .NET provides powerful APIs to extract hyperlink destinations with ease. This tutorial demonstrates step-by-step how to extract hyperlink destinations using C#.

#### Q: Can I selectively extract hyperlink destinations based on certain criteria?

A: Yes, you can selectively extract hyperlink destinations by iterating through the pages of the PDF document and filtering the desired hyperlink annotations based on your criteria.

#### Q: Is it possible to extract hyperlink destinations from password-protected PDF documents?

A: Aspose.PDF for .NET can extract hyperlink destinations from password-protected PDF documents as long as you provide the necessary authentication credentials when opening the document.

#### Q: How can I utilize the extracted hyperlink destinations in my application?

A: Once you've extracted the hyperlink destinations, you can use them to perform various actions, such as validating link URLs, creating reports, or implementing custom navigation.

#### Q: Are there any limitations when extracting hyperlink destinations?

A: While hyperlink destination extraction is powerful, it's essential to consider the structure of the PDF document. Hyperlinks embedded within complex graphics or multimedia content may require additional handling.

#### Q: Can I extract other attributes of hyperlinks, such as link types or coordinates?

A: The tutorial focuses on extracting hyperlink destinations. However, you can refer to the official Aspose.PDF documentation to explore advanced features, including extracting link types and coordinates.