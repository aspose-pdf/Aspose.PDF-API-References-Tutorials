---
title: Add Remove Javascript To PDF Document
linktitle: Add Remove Javascript To Doc
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add and remove JavaScript to PDF document using Aspose.PDF for .NET. Step-by-step guide with code tutorials for document-level scripting.
type: docs
weight: 30
url: /net/programming-with-document/addremovejavascripttodoc/
---
## Introduction

In this guide, we’ll walk through how to use Aspose.PDF for .NET to insert JavaScript into a PDF file and how to remove it when necessary. By the end of this tutorial, you’ll have a clear understanding of how to manipulate JavaScript in PDFs effortlessly.

## Prerequisites

Before we dive into the code, there are a few things you'll need to have set up:

1. Aspose.PDF for .NET: You’ll need the Aspose.PDF for .NET library installed in your project. If you don’t have it yet, grab the library from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net/).
2. IDE or Text Editor: You can use any .NET-compatible IDE like Visual Studio.
3. Basic C# Knowledge: This tutorial assumes you're comfortable with C# and familiar with PDF manipulation.
4. License: Make sure to apply a valid license to avoid limitations. You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).

## Import Packages

To begin using Aspose.PDF for .NET, you’ll need to import the necessary namespaces into your project. Here’s how:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

These two namespaces are essential. `Aspose.Pdf` allows you to work with PDF documents, while `System.Collections` will be used for handling JavaScript keys.

Let's break down the entire process of adding and removing JavaScript from a PDF into easy-to-follow steps.

## Step 1: Initialize a New PDF Document

The first thing you’ll need to do is create a new PDF document. This document will serve as our blank canvas for adding JavaScript.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

Here, we're initializing a new `Document` object and adding a blank page to it. Think of this as your PDF's foundation.

## Step 2: Add JavaScript to the PDF

Now that we have a document, it’s time to add some JavaScript to it. JavaScript in PDFs can be used to add custom behaviors, such as alerts or form validation.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

In this code snippet, we are adding two JavaScript functions (`func1` and `func2`) to the PDF. These functions could perform various tasks, depending on your needs. Here, we’re just calling a placeholder function called `hello()`.

## Step 3: Save the PDF with JavaScript

Once you’ve added the desired JavaScript, it’s time to save the PDF.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

This will save the document with JavaScript under the name `AddJavascript.pdf` in the specified directory (`dataDir`).

## Step 4: Load and View JavaScript in the Existing PDF

Let’s say you need to check or modify the JavaScript functions within an existing PDF. The first step is to load the PDF file and access the JavaScript keys.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

We’re loading the existing `AddJavascript.pdf` and storing the JavaScript keys in a list. The `Keys` property returns the names of all JavaScript functions attached to the document.

## Step 5: Display JavaScript Functions

Next, we can iterate through the JavaScript functions to see what’s available in the document.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

This will print out each JavaScript function name and its corresponding code to the console. It’s useful if you want to verify what functions are currently in the document.

## Step 6: Remove JavaScript from the PDF

Now, let’s say you want to remove a specific JavaScript function, like `func1`. Here’s how you can do that:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

The `Remove` method takes the name of the JavaScript function as an argument and deletes it from the document.

## Step 7: Verify JavaScript Removal

After removing the JavaScript, you can reprint the remaining functions to confirm that `func1` has been successfully deleted.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

This last part of the code ensures everything is in place and the JavaScript functions are updated correctly.

## Conclusion

Congratulations! You’ve just learned how to add and remove JavaScript from a PDF document using Aspose.PDF for .NET. This powerful feature can be utilized for a variety of tasks, from adding dynamic messages to performing custom calculations or validations. By manipulating JavaScript within a PDF, you can significantly enhance the user experience.

## FAQ's

### Can I add multiple JavaScript functions to a single PDF?
Absolutely! You can add as many JavaScript functions as you need using the `doc.JavaScript` collection.

### What happens if I try to remove a non-existent JavaScript function?
If the function doesn't exist, the `Remove` method won't throw an error, but it also won't remove anything.

### Is it possible to run JavaScript as soon as the PDF is opened?
Yes! You can configure JavaScript to run on certain triggers, such as opening the document or clicking a button.

### Can I edit the JavaScript after it’s been added to the PDF?
Yes, you can load an existing PDF, access its JavaScript, modify the code, and save the document again.

### Does removing JavaScript affect the rest of the PDF content?
No, removing JavaScript only affects the script. The content of the PDF remains unchanged.
