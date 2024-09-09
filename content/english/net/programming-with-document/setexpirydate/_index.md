---
title: Set Expiry Date In PDF File
linktitle: Set Expiry Date In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set an expiry date in PDF files using Aspose.PDF for .NET. Enhance document security with this step-by-step guide.
type: docs
weight: 300
url: /net/programming-with-document/setexpirydate/
---
## Introduction

In today's digital age, managing and securing documents is more crucial than ever. Imagine sending out a PDF that automatically becomes inaccessible after a certain date. Sounds like magic, right? Well, with Aspose.PDF for .NET, you can easily set an expiry date for your PDF files. This feature is particularly useful for sensitive documents that need to be restricted after a certain period. In this tutorial, we will walk you through the process of setting an expiry date in a PDF file step by step. So, grab your coding hat, and let’s dive in!

## Prerequisites

Before we get started, there are a few things you need to have in place:

1. Development Environment: Ensure you have a .NET development environment set up. This could be Visual Studio or any other IDE that supports .NET.
2. Aspose.PDF for .NET: You need to have the Aspose.PDF library installed. If you haven’t done this yet, you can download it from [here](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: This tutorial assumes you have a basic understanding of C# programming. If you're new to C#, don't worry! We'll keep it simple and straightforward.

## Import Packages

To get started with Aspose.PDF, you need to import the necessary namespaces in your C# project. This is how you can do it:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

These namespaces provide you access to the core functionalities required for working with PDF documents in Aspose.PDF.

## Step 1: Set Up Your Document Directory

First things first, you need to specify the path to your documents directory. This is where your output PDF will be saved. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where you want to save your PDF file. It’s like telling your program, “Hey, this is where I keep my files!”

## Step 2: Instantiate the Document Object

Next, you need to create a new instance of the `Document` class. This is your canvas where you will create your PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Think of the `Document` object as a blank sheet of paper. You can add content to it however you like!

## Step 3: Add a Page to the PDF

Now that you have your document set up, it’s time to add a page to it. This is where your content will go.

```csharp
doc.Pages.Add();
```

You just created a new page in your PDF. It’s like adding a new page in your notebook where you can jot down your thoughts.

## Step 4: Add Text to the Page

Let’s make this page a bit more interesting by adding some text. We’ll add a simple “Hello World” message.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

This line of code adds a text fragment to the first page of your PDF. It’s like writing a title at the top of your page!

## Step 5: Create JavaScript for Expiry Date

Now comes the fun part! You’ll create a JavaScript action that will check the expiry date of the PDF. If the current date exceeds the expiry date, a message will alert the user.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Here’s what’s happening:
- You define the expiry year and month.
- You get today’s date.
- You compare today’s date with the expiry date.
- If today’s date is past the expiry date, a message pops up!

## Step 6: Set JavaScript as PDF Open Action

Now, you need to set the JavaScript action as the open action for your PDF document. This means that the JavaScript will run as soon as the PDF is opened.

```csharp
doc.OpenAction = javaScript;
```

This line tells the PDF to execute the JavaScript when someone opens it. It’s like setting a reminder that goes off as soon as you open your calendar!

## Step 7: Save the PDF Document

Finally, it’s time to save your PDF document with the expiry date feature. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

This line saves your PDF to the specified directory with the name "SetExpiryDate_out.pdf". It’s like putting your finished artwork in a frame!

## Conclusion

And there you have it! You’ve successfully created a PDF file with an expiry date using Aspose.PDF for .NET. This feature not only enhances security but also ensures that sensitive information is kept under control. Whether you’re sending out contracts, reports, or any other important documents, setting an expiry date can be a game changer.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and convert PDF documents in .NET applications.

### Can I use Aspose.PDF for free?
Yes, you can use a free trial version of Aspose.PDF. You can download it [here](https://releases.aspose.com/).

### How do I purchase Aspose.PDF?
You can buy Aspose.PDF by visiting the [purchase page](https://purchase.aspose.com/buy).

### What if I need support?
If you have any questions or need assistance, you can visit the [Aspose support forum](https://forum.aspose.com/c/pdf/10).

### Can I get a temporary license for Aspose.PDF?
Yes, you can request a temporary license [here](https://purchase.aspose.com/temporary-license/).
