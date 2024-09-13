---
title: Get File Info In PDF File
linktitle: Get File Info In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetFileInfo in PDF file feature of Aspose.PDF for .NET to retrieve metadata information about a PDF document.
type: docs
weight: 180
url: /net/programming-with-document/getfileinfo/
---
## Introduction

Have you ever wondered what secrets lie within a PDF file? Whether it's the author, creation date, or even keywords, PDF documents often hold valuable metadata that can be crucial for various applications. In this tutorial, we will explore how to extract file information from a PDF using Aspose.PDF for .NET. This powerful library allows developers to manipulate PDF files with ease, making it a go-to choice for many. So, grab your coding hat, and let’s dive into the world of PDF metadata extraction!

## Prerequisites

Before we jump into the code, there are a few things you need to have in place:

1. Visual Studio: Ensure you have Visual Studio installed on your machine. This will be our development environment.
2. Aspose.PDF for .NET: You need to download and install the Aspose.PDF library. You can get it from the [download link](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: Familiarity with C# programming will help you understand the code snippets better.

## Import Packages

To get started, we need to import the necessary packages. Open your C# project in Visual Studio and add a reference to the Aspose.PDF library. You can do this by using NuGet Package Manager:

1. Right-click on your project in the Solution Explorer.
2. Select "Manage NuGet Packages."
3. Search for "Aspose.PDF" and install it.

Once you have the library installed, you can start writing your code.

## Step 1: Set Up Your Project

### Create a New Project

First things first, let’s create a new C# project in Visual Studio:

1. Open Visual Studio and select "Create a new project."
2. Choose "Console App (.NET Framework)" and click "Next."
3. Name your project (e.g., `PDFFileInfoExtractor`) and click "Create."

### Add the Aspose.PDF Reference

Now that your project is set up, you need to add the Aspose.PDF reference:

1. Right-click on your project in the Solution Explorer.
2. Select "Add" > "Reference."
3. In the Reference Manager, find and check Aspose.PDF, then click "OK."

## Step 2: Write the Code

### Initialize the Document

Now, let’s write the code to open a PDF document and extract its information. Start by adding the following using directive at the top of your `Program.cs` file:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Next, we’ll initialize the document:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

### Extract Document Information

Now that we have the PDF document open, let’s extract its metadata:

```csharp
// Get document information
DocumentInfo docInfo = pdfDocument.Info;
```

### Display the Information

Finally, let’s display the extracted information in the console:

```csharp
// Show document information
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Conclusion

Congratulations! You’ve successfully extracted file information from a PDF using Aspose.PDF for .NET. This powerful library not only allows you to read metadata but also provides a plethora of features for manipulating PDF files. Whether you’re developing a document management system or simply need to extract information for reporting, Aspose.PDF has got you covered. 

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that allows developers to create, manipulate, and convert PDF documents in .NET applications.

### How do I install Aspose.PDF?
You can install Aspose.PDF via NuGet Package Manager in Visual Studio or download it from the [download link](https://releases.aspose.com/pdf/net/).

### Can I extract images from a PDF using Aspose.PDF?
Yes, Aspose.PDF provides methods to extract images from PDF documents.

### Is there a free trial available for Aspose.PDF?
Yes, you can get a free trial from the [Aspose website](https://releases.aspose.com/).

### Where can I find support for Aspose.PDF?
You can find support and ask questions on the [Aspose forum](https://forum.aspose.com/c/pdf/10).
