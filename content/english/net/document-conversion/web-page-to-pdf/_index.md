---
title: Web Page To PDF
linktitle: Web Page To PDF
second_title: Aspose.PDF for .NET API Reference
description: Learn how to convert web pages to PDF using Aspose.PDF for .NET in this detailed, step-by-step tutorial.
type: docs
weight: 320
url: /net/document-conversion/web-page-to-pdf/
---
## Introduction

In today’s digital age, the ability to convert web pages into PDF documents is incredibly valuable. Whether you're looking to save an article for offline reading, create a report, or archive content from the web, having the right tools can make all the difference. One such tool is Aspose.PDF for .NET, a powerful library that allows developers to create and manipulate PDF documents seamlessly. In this guide, we’ll walk you through the process of converting a web page into a PDF using Aspose.PDF for .NET, breaking it down into manageable steps.

## Prerequisites

Before we dive into the code, let’s ensure you have everything you need to get started:

1. Visual Studio: Make sure you have Visual Studio installed on your machine. This is where you’ll write and execute your .NET code.
2. Aspose.PDF for .NET: You’ll need the Aspose.PDF library. You can download it from [here](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: Familiarity with C# programming will help you understand the examples better.
4. Internet Access: Since we’ll be fetching content from a web page, ensure your development environment has internet access.

## Import Packages

To get started, you need to import the necessary packages in your C# project. Here’s how:

### Create a New Project

First, open Visual Studio and create a new C# console application project. 

### Add Aspose.PDF Reference

Next, add a reference to the Aspose.PDF library. You can do this via NuGet Package Manager:

1. Right-click on your project in the Solution Explorer.
2. Select "Manage NuGet Packages."
3. Search for "Aspose.PDF" and click "Install."

### Import Required Namespaces

Once the library is added, open your `Program.cs` file and import the necessary namespaces at the top of the file:

```csharp
using System.IO;
using System;
using System.Net;
using Aspose.Pdf;
```

Now that we have everything set up, let’s break down the process of converting a web page to a PDF document step-by-step.

## Step 1: Define the Document Directory

First, you’ll want to define where the output PDF will be saved. This is done by specifying a path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Replace with your path
```

## Step 2: Create a Web Request

Next, you’ll need to create a request to fetch the content from the web page you want to convert. Here’s how you do it:

```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```

In this code, we’re creating a request to the Wikipedia main page. You can replace the URL with any web page of your choice.

## Step 3: Get the Response

Once you’ve set up the request, it’s time to get the response from the server. This involves sending the request and reading the response stream:

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

Here, we read the entire content returned by the server into a string variable. This is the content we’ll convert to PDF.

## Step 4: Load HTML Content into Memory

Now that we have the HTML content, we need to load it into a `MemoryStream` so that we can process it with Aspose.PDF:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
```

In this step, we’re converting the string response into a byte array and loading it into a `MemoryStream`. The `HtmlLoadOptions` allows us to specify the base URL for any relative links in the HTML.

## Step 5: Create a PDF Document

With the HTML content loaded, we can now create a PDF document from it:

```csharp
Document pdfDocument = new Document(stream, options);
```

This line of code initializes a new `Document` object, which represents the PDF we’re going to create.

## Step 6: Set Page Orientation

If you want to customize the PDF's layout, such as setting it to landscape mode, you can do so with the following code:

```csharp
options.PageInfo.IsLandscape = true;
```

This is optional but can be useful depending on the content you’re converting.

## Step 7: Save the PDF

Finally, it’s time to save the PDF document to the specified directory:

```csharp
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```

This line saves the PDF with the name `WebPageToPDF_out.pdf` in your specified documents directory.

## Step 8: Handle Exceptions

It’s always good practice to handle exceptions that might occur during the process. You can wrap your code in a try-catch block:

```csharp
try
{
    // All the previous code here
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

This way, if something goes wrong, you’ll get a message indicating what happened.

## Conclusion

And there you have it! You’ve successfully converted a web page into a PDF using Aspose.PDF for .NET. With just a few lines of code, you can automate the process of saving web content for later use. This can be incredibly useful for developers looking to create reports, archives, or simply save articles for offline reading. 

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that allows developers to create, manipulate, and convert PDF documents programmatically.

### Can I convert any web page to PDF?
Yes, as long as the web page is publicly accessible, you can convert it to PDF using Aspose.PDF.

### Is there a free trial available?
Yes, you can download a free trial of Aspose.PDF for .NET from [here](https://releases.aspose.com/).

### Where can I get support for Aspose.PDF?
You can get support from the Aspose community on their [support forum](https://forum.aspose.com/c/pdf/10).

### How can I obtain a temporary license?
You can apply for a temporary license on the [Aspose website](https://purchase.aspose.com/temporary-license/).
