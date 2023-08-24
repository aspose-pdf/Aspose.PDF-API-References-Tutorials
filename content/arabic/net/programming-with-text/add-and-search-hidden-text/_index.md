---
title: Add And Search Hidden Text In PDF File
linktitle: Add And Search Hidden Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to add and search hidden text in PDF file using Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-text/add-and-search-hidden-text/
---
In this tutorial, we will walk you through how to add and search hidden text in PDF file using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## 1. Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## 2. Creating the PDF document with hidden text

To get started, use the following code to create a new PDF document containing hidden text:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Create a document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Set text property - invisible
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Be sure to provide the desired path and filename for the PDF document.

## 3. Search for text in the document

Next, we will search the hidden text in the PDF document. Use the following code:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Do something with the fragments
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

This will search the hidden text in the second page of the PDF document and display the relevant information.

### Sample source code for Add And Search Hidden Text using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Create document with hidden text
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Set text property - invisible
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Search text in the document
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Do something with fragments
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Conclusion

Congratulation ! You have successfully added and found hidden text in a PDF document using Aspose.PDF for .NET. You can now apply this method to your own projects to manipulate and search hidden text in PDF files.

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a robust library that empowers developers to create, manipulate, and transform PDF documents within .NET applications.

#### Q: Can hidden text be used for watermarking purposes?

A: Absolutely! Hidden text can serve as an effective means of watermarking PDF documents, adding an extra layer of security.

#### Q: Is it possible to reveal hidden text in a PDF document?

A: Yes, the process of searching and revealing hidden text within a PDF document can be achieved using the techniques outlined in this tutorial.

#### Q: What other functionalities does Aspose.PDF for .NET offer?

A: Beyond hidden text manipulation, Aspose.PDF for .NET provides a wide array of features, including PDF generation, conversion, encryption, and more.