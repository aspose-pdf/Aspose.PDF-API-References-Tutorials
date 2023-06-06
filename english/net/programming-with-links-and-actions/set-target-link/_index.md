---
title: Set Target Link
linktitle: Set Target Link
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set a target link in a PDF file using Aspose.PDF for .NET.
type: docs
weight: 100
url: /net/programming-with-links-and-actions/set-target-link/
---

Learn how to set a target link in a PDF file using Aspose.PDF for .NET with this step-by-step guide.

## Step 1: Setting up the environment

Make sure you have set up your development environment with a C# project and the appropriate Aspose.PDF references.

## Step 2: Loading the PDF file

Set the directory path of your documents and upload the PDF file using the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load the PDF file
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Step 3: Editing the target link

Get the link annotation to modify using the following code:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

You can adjust the `[1]` indices to select a specific page or annotation.

Next, update the destination without updating the file:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

And if you also want to update the file:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Step 4: Save the document with the updated link

Save the document with the updated link using the `Save` method:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Step 5: Displaying the result

Display a message indicating that the target link was successfully configured and specify the location of the saved file:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Sample source code for Set Target Link using Aspose.Words for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load the PDF file
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Next line update destination, do not update file
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Next line update file
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Save the document with updated link
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Congratulation ! You now know how to set a target link in a PDF file using Aspose.PDF for .NET. Use this knowledge to customize links in your PDF documents and create interactive experiences for users.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.
