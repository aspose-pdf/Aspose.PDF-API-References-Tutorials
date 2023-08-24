---
title: Extract Highlighted Text In PDF File
linktitle: Extract Highlighted Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract highlighted text in PDF file using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 60
url: /sv/net/annotations/extracthighlightedtext/
---
To extract highlighted text in PDF file, you can use the Aspose.PDF for .NET API. This API provides a simple way to retrieve all the text that has been highlighted in a document.

## Step 1: Load the PDF document

The first step in extracting highlighted text in PDF file is to load the document using the Aspose.PDF for .NET API. You can do this by creating a new instance of the `Document` class and passing the path to the PDF document as a parameter. 

```csharp
// The path to the documents directory.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Step 2: Loop through all annotations

The next step is to loop through all the annotations in the PDF document. You can do this using a `foreach` loop, like so:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Code goes here
}
```

## Step 3: Filter text markup annotations

Inside the `foreach` loop, you will need to filter out all the annotations that are not text markup annotations. You can do this by checking if the annotation is an instance of the `TextMarkupAnnotation` class.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Code goes here
}
```

## Step 4: Retrieve highlighted text fragments

Once you have filtered out all the text markup annotations, you can retrieve the highlighted text fragments for each annotation. You can do this by calling the `GetMarkedTextFragments()` method on the `TextMarkupAnnotation` object.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Step 5: Display the highlighted text

Finally, you can display the highlighted text to the user. You can do this by looping through each `TextFragment` object in the `TextFragmentCollection` and calling the `Text` property.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Example source code for Extract Highlighted Text using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Conclusion

In this tutorial, we explored how to extract highlighted text from a PDF document using Aspose.PDF for .NET. By following the step-by-step guide and using the provided C# source code, developers can easily extract and manage highlighted text in their PDF documents.

### FAQ's for extract highlighted text in PDF file

#### Q: What are text markup annotations in a PDF document?

A: Text markup annotations are annotations that highlight or mark specific text in a PDF document. Examples of text markup annotations include highlights, underlines, and strikethroughs.

#### Q: Can I extract text from other types of annotations using Aspose.PDF for .NET?

A: Yes, Aspose.PDF for .NET provides various methods to extract text from different types of annotations, including text markup annotations, free text annotations, and more.

#### Q: Does Aspose.PDF for .NET support extracting text from password-protected PDF files?

A: Yes, Aspose.PDF for .NET supports extracting text from password-protected PDF files. You need to provide the correct password when loading the PDF document using the `Document` class.

#### Q: Can I filter highlighted text based on other criteria, such as color or author?

A: Yes, you can filter highlighted text based on other criteria, such as color, author, or creation date. Aspose.PDF for .NET provides methods to access and filter annotations based on their properties.

#### Q: Is it possible to save the extracted highlighted text to a separate file?

A: Yes, you can save the extracted highlighted text to a separate file or store it in a data structure for further processing or analysis.
