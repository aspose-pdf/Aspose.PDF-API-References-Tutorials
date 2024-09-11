---
title: Create Local Hyperlink In PDF File
linktitle: Create Local Hyperlink In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create local hyperlinks in PDF files using Aspose.PDF for .NET effortlessly with our step-by-step guide.
type: docs
weight: 40
url: /net/programming-with-links-and-actions/create-local-hyperlink/
---
## Introduction

In this guide, we’ll walk you through the process of creating local hyperlinks in a PDF file using Aspose.PDF for .NET. We will break down each step clearly, ensuring that even if you're new to the world of PDF manipulation, you’ll be able to follow along effortlessly.

## Prerequisites

Before diving headfirst into the code, let’s make sure you have everything you need:

1. Visual Studio: You’ll need this to develop your .NET applications. Download it from the [website](https://visualstudio.microsoft.com/).
2. Aspose.PDF for .NET: You can download this library via the [download link here](https://releases.aspose.com/pdf/net/). It comes with a rich set of features for PDF manipulation.
3. Basic Knowledge of C#: A little familiarity with C# programming will help, but don't worry; we’ll go through the code line by line.
4. .NET Framework: Ensure you have the .NET framework installed on your machine. You can check the requirements on the Aspose.PDF [documentation](https://reference.aspose.com/pdf/net/).

With these prerequisites set up, you’re ready to learn how to create local hyperlinks in your PDF documents!

## Import Packages

Now that you’re all prepped up, it’s time to import the necessary packages in your C# project. The Aspose.PDF library contains all the classes we need. Here’s how to do it:

### Open Your Project

Open your existing .NET project or create a new one in Visual Studio. If you're starting fresh, select “Create a new project” from the startup screen.

### Add Reference to Aspose.PDF

Right-click on "Dependencies" in your project folder in Solution Explorer. Select "Manage NuGet Packages," then search for `Aspose.PDF`. Install the latest version available. This will bring all the tools you need for creating and manipulating PDFs.

### Import Namespaces

At the top of your .cs file, add using directives for the Aspose.PDF library like this:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

This way, you’ll be able to access the library’s features.

Let’s break down the process of creating local hyperlinks into simple steps. Each step will be explained comprehensively to help you understand the logic behind it.

## Step 1: Set Up Document Instance

In this step, you'll create a new instance of the Document class, which represents the PDF file you will be working with.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Set your document directory
Document doc = new Document(); // Create Document instance
```
The `dataDir` variable is where your newly created PDF will reside. You’ll need to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path on your system. The `Document` class creates a new PDF document where we can add pages and links.

## Step 2: Add a Page to the Document

Next, you're going to add a page to your PDF document. 

```csharp
Page page = doc.Pages.Add(); // Add page to pages collection
```
The `Pages.Add()` method adds a new page to the document. This is where all your content will live.

## Step 3: Create a Text Fragment

Now, let’s create a piece of text that will act as a clickable link.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
The `TextFragment` represents a segment of text in the PDF. Here, we're creating a link that tells users it will take them to page 7.

## Step 4: Create Local Hyperlink

Here’s where the magic happens! You need to create a local hyperlink that will tell the text fragment where to point.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Create local hyperlink
link.TargetPageNumber = 7; // Set target page for link instance
text.Hyperlink = link; // Set TextFragment hyperlink
```
The `LocalHyperlink` class is what allows us to point to other pages in the same document. By setting `TargetPageNumber` to 7, you tell the hyperlink to jump to that specific page when clicked.

## Step 5: Add the Text Fragment to the Page

After setting up the hyperlink, it’s time to add our text fragment to the page we created.

```csharp
page.Paragraphs.Add(text); // Add text to paragraphs collection of Page
```
This line adds your clickable text to the page’s collection of paragraphs.

## Step 6: Create Another Text Fragment (Optional)

Let’s add another hyperlink to navigate back to page 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Create new TextFragment
text.IsInNewPage = true; // Add it to a new page
```
Creating a new `TextFragment` for the second link, we set `IsInNewPage` to true, indicating this text will go on a new page.

## Step 7: Set Up the Second Local Hyperlink

Just like before, you’ll create another local hyperlink for page 1.

```csharp
link = new LocalHyperlink(); // Create another local hyperlink instance
link.TargetPageNumber = 1; // Set Target page for second hyperlink
text.Hyperlink = link; // Set link for second TextFragment
```
This hyperlink targets page 1, allowing users to jump back when they reach the second page.

## Step 8: Add the Second Text Fragment to the New Page

Now, let’s add this text to its page.

```csharp
page.Paragraphs.Add(text); // Add text to paragraphs collection of page object
```
Similar to step 5, this line adds the new hyperlink text to the newly created page.

## Step 9: Save the Document

Finally, it’s time to save your hard work! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Specify output file name
doc.Save(dataDir); // Save updated document
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
This combines your directory path with the file name. The `Save()` method saves your document, and a confirmation message lets you know everything went smoothly!

## Conclusion

Creating local hyperlinks in PDF files using Aspose.PDF for .NET isn't just a cool trick; it's a practical feature that enhances navigation and user experience. You’re now equipped with the knowledge to point your readers directly to the information they need. Just think back to our initial analogy—no more lost souls wandering through endless pages.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that allows developers to create, manipulate, and convert PDF documents programmatically using the .NET framework.

### Can I create hyperlinks to external web pages?
Yes, Aspose.PDF also supports creating hyperlinks to external URLs aside from local hyperlinks within the PDF.

### Is there a free trial for Aspose.PDF?
Absolutely! You can access the free trial from the [site](https://releases.aspose.com/).

### What programming languages does Aspose support?
Aspose offers libraries for various programming languages, including Java, C++, and Python, among others.

### How do I obtain support for Aspose products?
You can seek support via the [Aspose Forum](https://forum.aspose.com/c/pdf/10).
