---
title: Add Remove Javascript To PDF Document
linktitle: Add Remove Javascript To Doc
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add and remove JavaScript to PDF document using Aspose.PDF for .NET. Step-by-step guide with code tutorials for document-level scripting.
type: docs
weight: 30
url: /de/net/programming-with-document/addremovejavascripttodoc/
---
To add and remove JavaScript to PDF document, we will utilize the Aspose.PDF for .NET library. This powerful library allows us to manipulate PDF files in .NET applications. Follow the step-by-step instructions below to add and remove JavaScript using Aspose.PDF for .NET.

## Step 1: Create a New PDF Document

Begin by creating a new instance of the `Document` class provided by Aspose.PDF for .NET. This will serve as the PDF document where we will add the JavaScript.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Step 2: Add JavaScript at the Document Level

To add JavaScript at the document level, use the `JavaScript` property of the `Document` class. Assign JavaScript functions to keys in the JavaScript dictionary.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

In this tutorial, we have added two JavaScript functions, `func1` and `func2`, to the PDF document.

## Step 3: Remove Document Level JavaScript

To remove JavaScript at the document level, load the PDF document and access the `JavaScript` dictionary. Iterate over the keys and remove the desired JavaScript function.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

In this tutorial, we remove the `func1` JavaScript function from the PDF document.

## Step 4: Save and Verify Changes

Save the modified PDF document and verify the changes.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

This code will save the modified PDF document and display the success message.

### Example source code for Add Remove Javascript from PDF documents using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Remove Document level JavaScript
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Conclusion

In this article, we have provided a step-by-step guide to adding and removing JavaScript from PDF documents using Aspose.PDF for .NET. By following the instructions and utilizing the provided code tutorials, you can easily incorporate JavaScript into your PDF documents and remove it when needed. JavaScript enables dynamic functionality and interactivity in your PDF files, enhancing the user experience.


### FAQ's for add remove javascript to PDF document

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that allows developers to manipulate PDF files in .NET applications effectively. It provides extensive features for working with PDF documents programmatically.

#### Q: How can I add JavaScript to a PDF document using Aspose.PDF for .NET?

A: You can add JavaScript at the document level using the `JavaScript` property of the `Document` class. Simply assign JavaScript functions to keys in the JavaScript dictionary.

#### Q: Can I remove JavaScript from a PDF document using Aspose.PDF for .NET?

A: Yes, you can remove JavaScript from a PDF document by accessing the `JavaScript` dictionary and removing the desired JavaScript function.

#### Q: Is Aspose.PDF for .NET suitable for professional projects?

A: Absolutely, Aspose.PDF for .NET is widely used in professional projects for PDF manipulation and generation tasks. It offers high performance and reliable functionality.

#### Q: What benefits does adding JavaScript to a PDF document provide?

A: Adding JavaScript to a PDF document enables you to create interactive and dynamic PDF files. You can implement form validation, perform calculations, and add various interactivity features to enhance user experience.