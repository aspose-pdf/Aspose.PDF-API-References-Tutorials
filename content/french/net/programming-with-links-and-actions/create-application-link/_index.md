---
title: Create Application Link In PDF File
linktitle: Create Application Link In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily create application links in PDF file with Aspose.PDF for .NET.
type: docs
weight: 20
url: /fr/net/programming-with-links-and-actions/create-application-link/
---
Creating an application link in PDF file allows you to create links to external applications, such as executable files or URLs. With Aspose.PDF for .NET, you can easily create app links by following the following source code:

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

### FAQ's for create application link in PDF file

#### Q: What are application links in PDF files?

A: Application links in PDF files allow you to create links that open external applications, such as executable files or URLs, when clicked. This feature enhances interactivity and provides a convenient way to connect users to external resources.

#### Q: How does Aspose.PDF for .NET facilitate the creation of application links?

A: Aspose.PDF for .NET simplifies the process of creating application links by providing a comprehensive set of tools and APIs. The step-by-step tutorial provided in this guide demonstrates how to add app links to your PDF documents.

#### Q: Can I customize the appearance of application links?

A: Absolutely! With Aspose.PDF for .NET, you have control over the appearance of application links. You can specify attributes such as color, style, and hover effects to ensure a visually appealing user experience.

#### Q: Are there any restrictions on the types of external applications I can link to?

A: Aspose.PDF for .NET allows you to link to a variety of external applications, including executable files, URLs, and documents. However, it's important to consider user security and compatibility when linking to executable files.

#### Q: How can I verify that my application links are working correctly?

A: By following the tutorial's instructions and using the provided sample code, you can confidently create functional application links. You can then test the links by opening the generated PDF document and clicking on the application links.

#### Q: Can I create multiple application links within a single PDF document?

A: Yes, you can create multiple application links within a single PDF document using the `LinkAnnotation` annotation. This allows you to provide users with access to different external applications from various sections of the document.

#### Q: Are there any security considerations when using application links?
A: When linking to executable files, it's important to ensure that the linked applications are secure and trustworthy. Additionally, consider user permissions and inform users about the potential launch of external applications.

#### Q: How do I add application links to URLs or web pages?

A: While this tutorial focuses on creating links to external applications, Aspose.PDF for .NET also supports creating hyperlinks to URLs or web pages. You can adapt the provided code to create web links within your PDF documents.

#### Q: Can I use Aspose.PDF for .NET to extract information from linked external applications?

A: Yes, Aspose.PDF for .NET provides capabilities to extract and manipulate information from linked external applications. You can explore the library's extensive features to perform various tasks related to linked content.