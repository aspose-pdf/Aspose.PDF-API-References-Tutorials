---
title: Update Link Text Color
linktitle: Update Link Text Color
second_title: Aspose.PDF for .NET API Reference
description: Learn how to update the text color of links in a PDF file with Aspose.PDF for .NET.
type: docs
weight: 130
url: /net/programming-with-links-and-actions/update-link-text-color/
---

Learn how to update the text color of links in a PDF file using Aspose.PDF for .NET with this step-by-step guide.

## Step 1: Setting up the environment

Make sure you have set up your development environment with a C# project and the appropriate Aspose.PDF references.

## Step 2: Loading the PDF file

Set the directory path of your documents and upload the PDF file using the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load the PDF file
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Step 3: Navigating Link Annotations

Loop through all the link annotations on the second page of the document using the following code:

```csharp
foreach(Annotation annotation in doc.Pages[1].Annotations)
{
     if (annotation is LinkAnnotation)
     {
         // Find the text under the annotation
         TextFragmentAbsorber ta = new TextFragmentAbsorber();
         Rectangle rect = annotation.Rect;
         rect.LLX -= 10;
         rect.LLY -= 10;
         rect.URX += 10;
         rect.URY += 10;
         ta.TextSearchOptions = new TextSearchOptions(rect);
         your.Visit(doc.Pages[1]);
         // Change text color.
         foreach(TextFragment tf in ta.TextFragments)
         {
             tf.TextState.ForegroundColor = Color.Red;
         }
     }
}
```

## Step 4: Save document with updated link text

Save the document with the updated link text using the `Save` method:

```csharp
dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
doc.Save(dataDir);
```

## Step 5: Displaying the result

Display a message that the link annotation text color was updated successfully and specify the location of the saved file:

```csharp
Console.WriteLine("\nText color of link annotations updated successfully.\nFile saved to location: " + dataDir);
```

### Sample source code for Update Link Text Color using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the PDF file
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is LinkAnnotation)
		{
			// Search the text under the annotation
			TextFragmentAbsorber ta = new TextFragmentAbsorber();
			Rectangle rect = annotation.Rect;
			rect.LLX -= 10;
			rect.LLY -= 10;
			rect.URX += 10;
			rect.URY += 10;
			ta.TextSearchOptions = new TextSearchOptions(rect);
			ta.Visit(doc.Pages[1]);
			// Change color of the text.
			foreach (TextFragment tf in ta.TextFragments)
			{
				tf.TextState.ForegroundColor = Color.Red;
			}
		}
	}
	dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
	// Save the document with updated link
	doc.Save(dataDir);
	Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Congratulation ! You now know how to update the text color of links in a PDF file using Aspose.PDF for .NET. Use this knowledge to customize the appearance of your links in PDF documents.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.
