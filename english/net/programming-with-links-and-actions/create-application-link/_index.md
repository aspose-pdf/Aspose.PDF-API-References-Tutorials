---
title: Create Application Link
linktitle: Create Application Link
second_title: Aspose.PDF for .NET API Reference
description: Easily create application links in your PDF files with Aspose.PDF for .NET.
type: docs
weight: 20
url: /net/programming-with-links-and-actions/create-application-link/
---

Creating an application link in a PDF document allows you to create links to external applications, such as executable files or URLs. With Aspose.PDF for .NET, you can easily create app links by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file to which you want to add an app link. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document to which we want to add an application link using the following code:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Step 4: Create the Application Link

In this step, we will create the application link using the `LinkAnnotation` annotation. We will specify the coordinates and area of the link, as well as the application launch action. Here is the corresponding code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Step 5: Save the updated file

Now let's save the updated PDF file using the `Save` method of the `document` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Sample source code for Create Application Link using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Create link
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Save updated document
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You now have a step-by-step guide to creating app links with Aspose.PDF for .NET. You can use this code to add links to external applications in your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on the advanced features of interactive links.
