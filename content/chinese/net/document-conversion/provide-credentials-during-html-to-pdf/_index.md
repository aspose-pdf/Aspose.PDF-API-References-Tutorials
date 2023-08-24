---
title: Provide Credentials During HTML To PDF
linktitle: Provide Credentials During HTML To PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert HTML to PDF by providing credentials with Aspose.PDF for .NET.
type: docs
weight: 240
url: /zh/net/document-conversion/provide-credentials-during-html-to-pdf/
---
In this tutorial, we will walk you through the process of converting an HTML file to PDF while providing credentials when accessing a secure URL using Aspose.PDF for .NET. By following the steps below, you will be able to convert HTML content to PDF using the appropriate credentials.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Fetch secure HTML content
In this step, we'll fetch secure HTML content from a URL using the appropriate credentials. Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a request for the URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// If needed for server, set credentials.
request.Credentials = CredentialCache.DefaultCredentials;
// Get the response.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Get the stream containing the content returned by the server.
Stream dataStream = response. GetResponseStream();
// Open the stream using a StreamReader for easy access.
StreamReader reader = new StreamReader(dataStream);
// Read the content.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where you want to save the resulting PDF file.

## Step 2: Convert HTML to PDF by providing credentials
Now we will load the retrieved HTML content and convert it to PDF format while providing the appropriate credentials. Use the following code:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Load the HTML file
Document pdfDocument = new Document(stream, options);
```

## Step 3: Saving the resulting PDF file
Finally, we will save the resulting PDF file. Use the following code:

```csharp
// Save the resulting PDF file
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

The code above saves the resulting PDF file with the filename `"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Example source code for Provide Credentials During HTML to PDF using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Create a request for the URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// If required by the server, set the credentials.
	request.Credentials = CredentialCache.DefaultCredentials;
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

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Load HTML file
	Document pdfDocument = new Document(stream, options);
	// Save resultant file
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting an HTML file to PDF while providing credentials when accessing a secure URL using Aspose.PDF for .NET. By following the instructions outlined above, you will be able to successfully convert HTML content to PDF while providing the correct credentials.

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a robust library that empowers developers to work with PDF documents in C# applications. It offers a wide range of functionalities, including HTML to PDF conversion.

#### Q: How can I fetch secure HTML content from a URL?

A: To fetch secure HTML content from a URL, you can use the `WebRequest` class in C#. Make sure to set the appropriate credentials using the `Credentials` property.

#### Q: What are the prerequisites for this tutorial?

A: Before proceeding with the tutorial, ensure that you have the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

#### Q: How does Aspose.PDF for .NET handle external resources while converting HTML to PDF?

A: Aspose.PDF for .NET provides the `HtmlLoadOptions` class to handle external resources during HTML to PDF conversion. You can set the external resource credentials using the `ExternalResourcesCredentials` property.

#### Q: Can I customize the filename for the resulting PDF file?

A: Yes, you can customize the filename for the resulting PDF file by modifying the code that saves the PDF document. Simply change the desired filename in the `pdfDocument.Save()` method.