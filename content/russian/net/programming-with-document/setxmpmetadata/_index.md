---
title: Set XMPMetadata In PDF File
linktitle: Set XMPMetadata In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set XMPMetadata in PDF file using Aspose.PDF for .NET. Follow this step-by-step guide.
type: docs
weight: 330
url: /ru/net/programming-with-document/setxmpmetadata/
---
In this article, we'll provide a step-by-step guide on how to use Aspose.PDF for .NET to set XMP metadata in a PDF file. We'll provide a full example source code at the end of the article.

## Step 1: Set the path to the document directory

Before we start, we need to set the path to the directory where our PDF document is located. We will store this path in a variable called "dataDir".

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Make sure to replace `YOUR DOCUMENT DIRECTORY` with the actual path to your PDF file.

## Step 2: Open the PDF File

The first step is to open the PDF file you want to set XMP metadata for. To do this, you'll need to create a new `Document` object and pass in the path to your PDF file.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Step 3: Set XMP Metadata Properties

Now that you have your PDF file open, you can start setting XMP metadata properties. The properties you set will depend on your specific needs, but here are some common properties you might want to set:

- `xmp:CreateDate`: The creation date of the PDF file.
- `xmp:Nickname`: A nickname or alias for the PDF file.
- `xmp:CustomProperty`: A custom property with a value you specify.

To set these properties, you can use the `Metadata` property of the `Document` object. Here's an example:

```csharp
// Set properties
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

In this tutorial, we're setting the creation date to the current date and time, the nickname to "Nickname", and a custom property to "Custom Value". You can replace these values with your own.

## Step 4: Save the PDF File

After you've set the XMP metadata properties, you need to save the PDF file. To do this, you can use the `Save` method of the `Document` object and pass in the path to where you want to save the updated PDF file.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Save document
pdfDocument.Save(dataDir);
```

### Example Source Code for Set XMPMetadata using Aspose.PDF for .NET

Here's the complete example source code for setting XMPMetadata using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Set properties
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Save document
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

Aspose.PDF for .NET offers a straightforward way to set XMP metadata in PDF files, enabling you to add descriptive information and properties to your documents. The step-by-step guide provided above shows you how to set various XMP metadata properties using C# source code. Additionally, you can customize the XMP metadata to match your specific needs and business requirements. With Aspose.PDF for .NET, managing PDF metadata becomes efficient and allows for better organization and searchability of your PDF documents.

### FAQ's forSet XMPMetadata in PDF file

#### Q: What is XMP metadata in a PDF file, and why is it important?

A: XMP (Extensible Metadata Platform) is a standard for embedding metadata in various file formats, including PDF. XMP metadata in a PDF file allows you to add descriptive information and properties to the document, such as creation date, author, title, keywords, and custom properties. It is essential for better organization, searchability, and archiving of PDF documents.

#### Q: Can I set other XMP metadata properties besides the ones mentioned in the example?

A: Yes, you can set a wide range of XMP metadata properties depending on your specific requirements. Some common properties include `dc:title` (document title), `dc:creator` (document creator), `dc:description` (document description), `pdf:Keywords` (document keywords), and more. The XMP specification offers various standard namespaces and custom namespaces for setting different types of metadata.

#### Q: Is it possible to retrieve and read XMP metadata from an existing PDF file?

A: Yes, Aspose.PDF for .NET provides the ability to read and retrieve XMP metadata from an existing PDF file. You can use the `Metadata` property of the `Document` class to access the XMP metadata and retrieve the values of specific properties.