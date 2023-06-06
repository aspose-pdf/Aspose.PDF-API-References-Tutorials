---
title: Extract Signature Info
linktitle: Extract Signature Info
second_title: Aspose.PDF for .NET API Reference
description: Extracting signature information using Aspose.PDF for .NET.
type: docs
weight: 80
url: /net/programming-with-security-and-signatures/extract-signature-info/
---

The process of extracting signature information from a PDF document can be quite useful in various scenarios. Whether you need to validate the authenticity of a signed document or analyze the certificate used for the signature, the Aspose.PDF for .NET library provides a convenient solution. In this tutorial, we will guide you through the step-by-step process of extracting signature information using the C# source code provided.

## Requirements

Before we begin, make sure you have the following prerequisites in place:

1. Basic knowledge of C# programming language.
2. Aspose.PDF for .NET library installed on your system.
3. A valid PDF document with one or more signature fields.

Now, let's dive into the implementation details.

## Step 1: Importing the Required Libraries

To get started, you need to import the necessary libraries into your C# project. In this case, we need to import the `Aspose.Pdf` and `System.IO` namespaces. This can be done by adding the following code at the beginning of your C# file:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Step 2: Setting the Document Path

Next, you need to set the path to the PDF document you want to extract the signature information from. Replace `"YOUR DOCUMENTS DIRECTORY"` in the following code snippet with the actual path to your document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Step 3: Extracting Signature Information

Now, let's move on to the main part of the code where we extract the signature information from the PDF document. We iterate through each field in the document's form and check if it is a signature field. If a signature field is found, we proceed with extracting the certificate. Add the following code snippet:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Extract the certificate
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Step 4: Extracting the Certificate

In this step, we extract the certificate from the signature field and save it as a file. The extracted certificate can be further analyzed or used for validation purposes. The code snippet below demonstrates the extraction and saving process:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Step 5

: Saving the Certificate

Finally, we save the extracted certificate as a file. In this example, the certificate is saved with the name "input.cer" in the specified directory. You can modify the code to suit your requirements. Here's the code snippet for saving the certificate:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

That's it! You have successfully extracted signature information using Aspose.PDF for .NET. Feel free to integrate this code into your own applications or modify it according to your needs.

### Sample source code for Extract Signature Info using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we walked through a step-by-step guide on how to extract signature information from a PDF document using the Aspose.PDF for .NET library. We covered the process of importing the required libraries, setting the document path, extracting signature information, extracting the certificate, and saving it to a file. By following these steps, you can easily retrieve signature details and work with them as needed.
