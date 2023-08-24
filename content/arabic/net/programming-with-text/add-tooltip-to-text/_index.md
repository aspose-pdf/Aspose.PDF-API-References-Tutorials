---
title: Add Tooltip To Text In PDF File
linktitle: Add Tooltip To Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add tooltips to text in PDF file using Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-text/add-tooltip-to-text/
---
This tutorial will guide you through the process of adding tooltips to text in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add tooltips to text, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a sample document with text
Create a new `Document` object and add pages with text fragments. In the provided code, two text fragments are added to the document with the respective tooltip text.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Step 5: Open the document and find the text fragments
Load the created document using the `Document` constructor and find the text fragments that need tooltips using `TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Step 6: Add tooltips to the text fragments
Loop through the extracted text fragments and create invisible buttons at their positions. Assign the desired tooltip text to the `AlternateName` property of the `ButtonField`. Add the button fields to the document's form.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Step 7: Repeat for additional text fragments with long tooltips
Repeat steps 5 and 6 for text fragments with long tooltips. Modify the search criteria and tooltip text accordingly.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Step 8: Save the modified document
Save the modified PDF document using the `Save` method of the `Document` object.

```csharp
document. Save(outputFile);
```

### Sample source code for Add Tooltip To Text using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Create sample document with text
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Open document with text
Document document = new Document(outputFile);
// Create TextAbsorber object to find all the phrases matching the regular expression
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Accept the absorber for the document pages
document.Pages.Accept(absorber);
// Get the extracted text fragments
TextFragmentCollection textFragments = absorber.TextFragments;
// Loop through the fragments
foreach (TextFragment fragment in textFragments)
{
	// Create invisible button on text fragment position
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// AlternateName value will be displayed as tooltip by a viewer application
	field.AlternateName = "Tooltip for text.";
	// Add button field to the document
	document.Form.Add(field);
}
// Next will be sapmle of very long tooltip
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Set very long text
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Save document
document.Save(outputFile);
```

## Conclusion
You have successfully added tooltips to text in a PDF document using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.

## FAQs

#### Q: What is the focus of this tutorial?

A: This tutorial focuses on adding tooltips to text within a PDF file using the Aspose.PDF for .NET library. The provided C# source code demonstrates the steps required to achieve this.

#### Q: Which namespaces need to be imported for this tutorial?

A: In the code file where you want to add tooltips to text, import the following namespaces at the beginning of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Q: How do I specify the document directory?

A: In the code, find the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How can I create a sample document with text?

A: In Step 4, you'll create a new `Document` object and add pages with text fragments. The code provided adds two text fragments with respective tooltip text.

#### Q: How do I open the document and find the text fragments?

A: In Step 5, you'll load the created document using the `Document` constructor and find the text fragments requiring tooltips using the `TextFragmentAbsorber`.

#### Q: How do I add tooltips to the text fragments?

A: In Step 6, you'll loop through the extracted text fragments and create invisible buttons at their positions. The tooltip text is assigned to the `AlternateName` property of the `ButtonField`, which is added to the document's form.

#### Q: How do I repeat the process for additional text fragments with long tooltips?

A: For text fragments with long tooltips, repeat Steps 5 and 6. Modify the search criteria and tooltip text accordingly.

#### Q: How do I save the modified document?

A: In Step 8, you'll save the modified PDF document using the `Save` method of the `Document` object.

#### Q: What is the main takeaway from this tutorial?

A: By following this tutorial, you've learned how to enhance your PDF document by adding tooltips to text using Aspose.PDF for .NET. This can provide valuable additional information for readers when they interact with the PDF content.