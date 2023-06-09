---
title: Set Destination Link
linktitle: Set Destination Link
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set a destination link in a PDF file using Aspose.PDF for .NET.
type: docs
weight: 90
url: /content/net/programming-with-links-and-actions/set-destination-link/
---

Learn how to set a destination link in a PDF file using Aspose.PDF for .NET with this step-by-step guide.

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

## Step 3: Editing the destination link

Get the link annotation to modify using the following code:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

You can adjust the `[1]` indices to select a specific page or annotation.

Next, edit the link by changing the link action and setting the target as a web address:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## Step 4: Save the document with the updated link

Save the document with the updated link using the `Save` method:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## Step 5: Displaying the result

Display a message indicating that the destination link was successfully configured and specify the location of the saved file:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Sample source code for Set Destination Link using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the PDF file
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Get the first link annotation from first page of document
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Modification link: change link action and set target as web address
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Save the document with updated link
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Congratulation ! You now know how to set a destination link in a PDF file using Aspose.PDF for .NET. Use this knowledge to customize links in your PDF documents and create interactive experiences for users.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.