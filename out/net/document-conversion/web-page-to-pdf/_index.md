---
title: Web Page to PDF
linktitle: Web Page to PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert web page to PDF using Aspose.PDF for .NET.
type: docs
weight: 320
url: /content/net/document-conversion/web-page-to-pdf/
---

In this tutorial, we will guide you step by step on how to convert a web page to PDF using the Aspose.PDF for .NET library. We will explain the provided C# source code and show you how to implement it in your own projects. By the end of this tutorial, you will be able to convert web pages to PDF documents effortlessly.

## Introduction
Converting web pages to PDF format is a common requirement in many applications. By converting web content to PDF, you can easily preserve the layout, formatting, and images of the original web page. Aspose.PDF for .NET is a powerful library that allows you to perform this conversion efficiently and accurately.

## Requirements
Before we get started, make sure you have the following prerequisites in place:
- Visual Studio installed on your machine
- Aspose.PDF for .NET library (you can download it from the official Aspose website)
- Basic knowledge of C# programming


## Step 1: Define the Document Directory
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
Replace `"YOUR DOCUMENT DIRECTORY"` with the path where you want to save the generated PDF file.

## Step 2: Create a Web Request
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Create a web request object and specify the URL of the web page you want to convert. You can replace the URL with any desired web page.

## Step 3: Get the Web Response
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Send the web request and retrieve the response from the server.

## Step 4: Read the Web Content
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
Read the content of the web page using a `StreamReader` and store it in the `responseFromServer` variable.

## Step 5: Convert HTML to PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
Create a `MemoryStream` object to load the web page content. Then, create an instance of `HtmlLoadOptions` and pass the base URL of the web page. Next, create a `Document` object using the loaded stream and the HTML load options. Set the `IsLandscape` property to `true` if you want the PDF to be in landscape orientation. Finally, save the PDF document to the specified directory

.

## Step 6: Handle Exceptions
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Catch any exceptions that may occur during the conversion process and display the error message.

### Example source code for Web Page to PDF using Aspose.Words for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Create a request for the URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// If required by the server, set the credentials.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Time out in miliseconds before the request times out
	// Request.Timeout = 100;

	// Get the response.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Get the stream containing content returned by the server.
	Stream dataStream = response.GetResponseStream();
	// Open the stream using a StreamReader for easy access.
	StreamReader reader = new StreamReader(dataStream);
	// Read the content.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Load HTML file
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Save output as PDF format
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we have learned how to convert a web page to PDF using the Aspose.PDF for .NET library. We went through the step-by-step guide explaining the provided C# source code. By following these instructions, you can easily integrate web page to PDF conversion functionality into your own .NET applications.