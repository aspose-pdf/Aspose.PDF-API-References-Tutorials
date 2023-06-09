---
title: Get Hyperlink Text
linktitle: Get Hyperlink Text
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract hyperlink text from a PDF file using Aspose.PDF for .NET.
type: docs
weight: 70
url: /net/programming-with-links-and-actions/get-hyperlink-text/
---

Learn how to extract text from hyperlinks in a PDF file using Aspose.PDF for .NET with this step-by-step guide.

## Step 1: Setting up the environment

Make sure you have set up your development environment with a C# project and the appropriate Aspose.PDF references.

## Step 2: Loading the PDF file

Set the directory path of your documents and upload the PDF file using the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load the PDF file
Document document = new Document(dataDir + "input.pdf");
```

## Step 3: Navigating through the pages of the document

Iterate through each page of the document using a `foreach` loop:

```csharp
foreach(Page page in document.Pages)
{
     // Display link annotations
     ShowLinkAnnotations(page);
}
```

## Step 4: Error Handling

Add error handling to catch any exception and display the corresponding error message:

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### Sample source code for Get Hyperlink Text using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the PDF file
	Document document = new Document(dataDir + "input.pdf");
	// Iterate through each page of PDF
	foreach (Page page in document.Pages)
	{
		// Show link annotation
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Congratulation ! You now know how to extract hyperlink text from a PDF file using Aspose.PDF for .NET. You can use this knowledge to deal with hyperlinks in your projects and automate tasks related to PDF files.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.
