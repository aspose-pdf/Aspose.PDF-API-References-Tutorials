---
title: Specify Page When Viewing
linktitle: Specify Page When Viewing
second_title: Aspose.PDF for .NET API Reference
description: Learn how to specify a page when viewing a PDF using Aspose.PDF for .NET.
type: docs
weight: 110
url: /net/programming-with-links-and-actions/specify-page-when-viewing/
---

Learn how to specify a page when viewing a PDF file using Aspose.PDF for .NET with this step-by-step guide.

## Step 1: Setting up the environment

Make sure you have set up your development environment with a C# project and the appropriate Aspose.PDF references.

## Step 2: Loading the PDF file

Set the directory path of your documents and upload the PDF file using the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load the PDF file
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Step 3: Specifying the target page

Get the target page instance using the following code:

```csharp
Page page2 = doc.Pages[2];
```

You can adjust the index `[2]` to select the desired page.

## Step 4: Configuring the zoom setting

Create a variable to set the target page zoom factor:

```csharp
double zoom = 1;
```

You can adjust the zoom value according to your needs.

## Step 5: Create the navigation action

Create an instance of the navigation action using the specified target page:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Step 6: Setting the destination

Set the destination to go to the target page using coordinates and zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Step 7: Configuring the Document Open Action

Set the document open action with the created navigation action:

```csharp
doc. OpenAction = action;
```

## Step 8: Save the updated document

Save the updated document using the `Save` method:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Sample source code for Specify Page When Viewing using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load the PDF file
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Get the instance of second page of document
Page page2 = doc.Pages[2];
// Create the variable to set the zoom factor of target page
double zoom = 1;
// Create GoToAction instance
GoToAction action = new GoToAction(doc.Pages[2]);
// Go to 2 page
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Set the document open action
doc.OpenAction = action;
// Save updated document
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusion

Congratulation ! You now know how to specify a page when viewing a PDF using Aspose.PDF for .NET. Use this knowledge to customize the user viewing experience in your PDF documents.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.
