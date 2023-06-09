---
title: Remove Open Action
linktitle: Remove Open Action
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove the open action from a PDF using Aspose.PDF for .NET.
type: docs
weight: 80
url: /content/net/programming-with-links-and-actions/remove-open-action/
---

Learn how to remove the open action from a PDF file using Aspose.PDF for .NET with this step-by-step guide.

## Step 1: Setting up the environment

Make sure you have set up your development environment with a C# project and the appropriate Aspose.PDF references.

## Step 2: Loading the PDF file

Set the directory path of your documents and upload the PDF file using the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open the document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Step 3: Deleting the open action

Remove the open action from the document by setting the `OpenAction` property to null:

```csharp
document. OpenAction = null;
```

## Step 4: Save the updated document

Save the updated document using the `Save` method:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Step 5: Displaying the result

Display a message indicating that the open action was successfully removed and specify the location of the saved file:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Sample source code for Remove Open Action using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Remove document open action
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Save updated document
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Congratulation ! Now you know how to remove the open action from a PDF using Aspose.PDF for .NET. Use this knowledge to customize the properties and behavior of PDF files in your projects.

Now that you've completed this guide, you can apply these concepts to your own projects and further explore the features offered by Aspose.PDF for .NET.