---
title: Add Java Script To PDF File
linktitle: Add Java Script PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add JavaScript to PDF file using Aspose.PDF for .NET. Step-by-step guide with code tutorials for document and page level scripting.
type: docs
weight: 10
url: /net/programming-with-document/addjavascripttopage/
---
To add JavaScript to a PDF file, we will use Aspose.PDF for .NET. This library provides a simple and efficient way to work with PDF files in .NET applications. The following steps will guide you through the process of adding JavaScript to a PDF file using Aspose.PDF for .NET.

## Step 1: Load the PDF File

The first step is to load the PDF file that you want to add JavaScript to. You can do this using the `Document` class provided by Aspose.PDF for .NET. The `Document` class provides methods for loading, saving, and manipulating PDF files.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load an existing PDF files
Document doc = new Document(dataDir + "input.pdf");
```

## Step 2: Add JavaScript at Document Level

To add JavaScript at the document level, we will use the `JavascriptAction` class provided by Aspose.PDF for .NET. This class allows you to specify the JavaScript statement that you want to add to the PDF file.

```csharp
// Adding JavaScript at Document Level
// Instantiate JavascriptAction with desired JavaScript statement
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assign JavascriptAction object to desired action of Document
doc.OpenAction = javaScript;
```

In this tutorial, we are adding a JavaScript statement that will print the PDF file with the specified options when the document is opened.

## Step 3: Add JavaScript at Page Level

To add JavaScript at the page level, we will use the `JavascriptAction` class and the `Actions` property provided by Aspose.PDF for .NET. This property allows you to specify JavaScript statements that will be executed when the page is opened or closed.

```csharp
// Adding JavaScript at Page Level
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

In this tutorial, we are adding JavaScript statements that will display an alert message when the page is opened or closed.

## Step 4: Save the PDF File

After you have added the JavaScript to the PDF file, you need to save the modified file. You can do this using the `Save` method provided by the `Document` class.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Save PDF Document
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

This code will save the modified PDF file to the specified directory.

### Example source code for Add Java Script To Page using Aspose.PDF for .NET

```csharp
            
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load an existing PDF files
Document doc = new Document(dataDir + "input.pdf");

// Adding JavaScript at Document Level
// Instantiate JavascriptAction with desried JavaScript statement
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assign JavascriptAction object to desired action of Document
doc.OpenAction = javaScript;

// Adding JavaScript at Page Level
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Save PDF Document
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Conclusion

In this article, we have explained how to add JavaScript to a PDF file at both the document level and the page level using Aspose.PDF for .NET. We have provided step-by-step instructions and included the full source code for each example. With this knowledge, you can add JavaScript to your PDF files and customize their behavior according to your needs.


### FAQ's for add java script to PDF file

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables developers to work with PDF files in .NET applications. It provides a wide range of features for creating, modifying, and manipulating PDF documents.

#### Q: Can I add JavaScript to a PDF document using Aspose.PDF for .NET?

A: Yes, Aspose.PDF for .NET allows you to add JavaScript to both the document level and the page level of a PDF file, enabling you to create dynamic and interactive PDF documents.

#### Q: How do I load an existing PDF file using Aspose.PDF for .NET?

A: You can load an existing PDF file using the `Document` class and its methods, as shown in the step-by-step guide.

#### Q: What types of JavaScript actions can I add to a PDF document?

A: With Aspose.PDF for .NET, you can add a wide variety of JavaScript actions, such as printing, alert messages, form field manipulation, and more.

#### Q: Is Aspose.PDF for .NET suitable for commercial projects?

A: Yes, Aspose.PDF for .NET is a reliable and robust library that is commonly used in commercial projects for PDF manipulation and generation tasks.


