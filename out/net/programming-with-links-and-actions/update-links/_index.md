---
title: Update Links
linktitle: Update Links
second_title: Aspose.PDF for .NET API Reference
description: Learn how to update links in a PDF file with Aspose.PDF for .NET.
type: docs
weight: 120
url: /content/net/programming-with-links-and-actions/update-links/
---

Learn how to update links in a PDF file using Aspose.PDF for .NET with this step-by-step guide.

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

## Step 3: Editing the link

Get the link annotation to modify using the following code:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

You can adjust the `[1]` indices to select a specific page or annotation.

Next, modify the link by changing the destination:

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

The first parameter represents the subject of the document, the second is the destination page number. The fifth argument is the zoom factor when displaying the respective page. When set to 2, the page will be displayed at 200% zoom.

## Step 4: Save the document with the updated link

Save the document with the updated link using the `Save` method:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## Step 5: Displaying the result

Display a message indicating that the links were updated successfully and specify the location of the saved file:

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### Sample source code for Update Links using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the PDF file
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Get the first link annotation from first page of document
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Modification link: change link destination
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// Specify the destination for link object
	// The first parameter is document object, second is destination page number.
	// The 5ht argument is zoom factor when displaying the respective page. When using 2, the page will be displayed in 200% zoom
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// Save the document with updated link
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Congratulation ! You now know how to update links in a PDF file using Aspose.PDF for .NET. Use this knowledge to customize links in your PDF documents and create interactive experiences for users.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.