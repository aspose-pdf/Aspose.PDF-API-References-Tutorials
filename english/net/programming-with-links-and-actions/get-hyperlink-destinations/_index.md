---
title: Get Hyperlink Destinations
linktitle: Get Hyperlink Destinations
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract hyperlink destinations from a PDF file using Aspose.PDF for .NET.
type: docs
weight: 60
url: /net/programming-with-links-and-actions/get-hyperlink-destinations/
---

Aspose.PDF for .NET is a powerful library for manipulating and extracting information from PDF files using the C# programming language. In this tutorial, we will focus on extracting hyperlink destinations from a PDF file using Aspose.PDF for .NET.

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

### Sample source code for Get Hyperlink Destinations using Aspose.Words for .NET 
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