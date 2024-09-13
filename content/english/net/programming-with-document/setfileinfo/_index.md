---
title: Set File Info In PDF File
linktitle: Set File Info In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set file info in PDF documents using Aspose.PDF for .NET with this step-by-step guide. Enhance your PDFs with metadata easily.
type: docs
weight: 310
url: /net/programming-with-document/setfileinfo/
---
## Introduction

When it comes to managing PDF files, having control over document metadata is crucial. Whether you're looking to add author information, keywords, or even a subject line, Aspose.PDF for .NET provides a seamless way to set file info in your PDF documents. This tutorial will guide you through the process step-by-step, ensuring you understand each part of the code as we go along. So, grab your coding hat, and let’s dive into the world of PDF manipulation!

## Prerequisites

Before we get started, there are a few things you need to have in place:

1. Visual Studio: Ensure you have Visual Studio installed on your machine. This is where you'll be writing and executing your .NET code.
   
2. Aspose.PDF for .NET: You’ll need to download and install the Aspose.PDF library. You can get it from the [Aspose Downloads page](https://releases.aspose.com/pdf/net/).

3. Basic Knowledge of C#: Familiarity with C# programming will help you understand the code snippets we’ll be using.

4. A PDF File: Have a sample PDF file ready that you want to modify. For this tutorial, we’ll refer to it as `SetFileInfo.pdf`.

Once you have all that set up, we’re ready to jump into the code!

## Import Packages

To get started, you need to import the necessary packages that will allow you to work with PDF files. In your C# project, add the following using directives at the top of your code file:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

These namespaces provide access to the classes and methods needed to manipulate PDF documents effectively.

## Step 1: Define the Document Directory

First things first, you need to specify the directory where your PDF file is located. This is crucial because you’ll be opening the file from this path.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Explanation: Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the folder containing your `SetFileInfo.pdf`. This tells your program where to look for the PDF file.

## Step 2: Open the PDF Document

Next, let’s open the PDF document that you want to modify. This is done using the `Document` class from the Aspose.PDF library.

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

Explanation: Here, we create a new instance of the `Document` class and pass the path of the PDF file. This loads the document into memory, ready for editing.

## Step 3: Create Document Info Object

Now that we have the document open, we need to create an object that will hold the document information.

```csharp
// Specify document information
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

Explanation: The `DocumentInfo` class allows us to set various metadata properties for the PDF. This object will be used to store information like the author, creation date, and more.

## Step 4: Set Document Metadata

With the `DocumentInfo` object ready, it’s time to populate it with the relevant metadata. This is where you can specify the author, creation date, keywords, modification date, subject, and title of the document.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

Explanation: Each line sets a specific property of the document. For example, `docInfo.Author` sets the author’s name, while `docInfo.CreationDate` sets the date the document was created. You can customize these values as needed.

## Step 5: Save the Document

After setting the desired metadata, the next step is to save the modified PDF. You need to specify a new path for the output file.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
// Save output document
pdfDocument.Save(dataDir);
```

Explanation: Here, we append `_out.pdf` to the original file name to create a new file for the modified document. The `Save` method then writes the changes to this new file.

## Step 6: Confirm the Changes

Finally, it’s always a good idea to confirm that the information has been set correctly. You can do this by printing a success message to the console.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Explanation: This line outputs a message indicating that the file has been successfully saved, along with the path to the new file. It’s a simple way to ensure everything went according to plan.

## Conclusion

Setting file info in PDF documents using Aspose.PDF for .NET is a straightforward process that can greatly enhance the usability of your PDFs. By following these steps, you can easily add metadata like the author, creation date, and more, making your documents more informative and professional. Whether you're developing applications that generate PDFs or simply need to manage your documents better, Aspose.PDF provides the tools you need to get the job done efficiently.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and convert PDF documents programmatically.

### Can I use Aspose.PDF for free?
Yes, Aspose offers a free trial version which you can use to evaluate the library. Visit the [Free trial page](https://releases.aspose.com/) for more information.

### Where can I find the documentation?
The complete documentation for Aspose.PDF can be found [here](https://reference.aspose.com/pdf/net/).

### How do I purchase Aspose.PDF?
You can buy the license for Aspose.PDF through the [purchase page](https://purchase.aspose.com/buy).

### What if I need support?
If you have any questions or need assistance, you can visit the [Aspose Support Forum](https://forum.aspose.com/c/pdf/10).
