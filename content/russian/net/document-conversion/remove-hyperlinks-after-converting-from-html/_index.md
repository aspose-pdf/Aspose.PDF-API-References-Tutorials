---
title: Remove Hyperlinks After Converting From Html
linktitle: Remove Hyperlinks After Converting From Html
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to remove hyperlinks after converting HTML to PDF using Aspose.PDF for .NET.
type: docs
weight: 250
url: /ru/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
In this tutorial, we'll walk you through the process of removing hyperlinks from a PDF file generated from an HTML file using Aspose.PDF for .NET. Hyperlinks are clickable links that may redirect to other pages or websites. By following the steps below, you will be able to remove hyperlinks from the resulting PDF file.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading HTML file and removing hyperlinks
At this step, we will load the HTML file and remove the hyperlinks from the resulting PDF document. Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the HTML file using the HTML loading options
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Browse the annotations of the first page of the document
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Check if the annotation is a link
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Check if the action is of type GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Use a text fragment absorber to find matching text fragments
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Loop through matching text fragments and remove attributes from hyperlinks
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Remove the annotation from the page
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your HTML file is located.

## Step 2: Saving the resulting PDF file
Finally, we'll save the resulting PDF file without the hyperlinks. Use the following code:

```csharp
// Save the resulting PDF file
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

The code above saves the resulting PDF file with the filename `"RemoveHyperlinksFromText_out.pdf"`.

### Example source code for Remove Hyperlinks After Converting From Html using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Conclusion
In this tutorial, we covered the step-by-step process of removing hyperlinks from a PDF file generated from an HTML file using Aspose.PDF for .NET. By following the instructions described above, you will be able to successfully remove hyperlinks from the resulting PDF file.

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents in C# applications. It offers a wide range of functionalities, including the ability to convert HTML files to PDF and manipulate PDF content.

#### Q: Why would I want to remove hyperlinks from a PDF file?

A: There are various reasons for removing hyperlinks from a PDF file. For example, you might want to eliminate external links for printing or archiving purposes or ensure that the PDF content is not navigable via hyperlinks.

#### Q: How can I load an HTML file and remove hyperlinks using Aspose.PDF for .NET?

A: To load an HTML file and remove hyperlinks, you can use Aspose.PDF for .NET's `HtmlLoadOptions` class. Iterate through the annotations of the PDF pages to find link annotations and modify their attributes.

#### Q: Can I customize the output filename for the resulting PDF?

A: Yes, you can customize the output filename for the resulting PDF file by modifying the code that saves the PDF document. Simply change the desired filename in the `doc.Save()` method.

#### Q: Is it possible to selectively remove hyperlinks based on certain criteria?

A: Yes, you can selectively remove hyperlinks based on specific criteria. For example, you can choose to remove only external links or links pointing to specific URLs.