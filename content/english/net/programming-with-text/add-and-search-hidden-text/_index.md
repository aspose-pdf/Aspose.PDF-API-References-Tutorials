---
title: Add And Search Hidden Text In PDF File
linktitle: Add And Search Hidden Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn to add and search for hidden text in PDF documents using Aspose.PDF for .NET. Step-by-step guide with code examples included.
type: docs
weight: 20
url: /net/programming-with-text/add-and-search-hidden-text/
---
## Introduction

In this tutorial, we’ll take you through a step-by-step guide on how to add and search hidden text in a PDF file using Aspose.PDF for .NET. Whether you’re a seasoned developer or a newbie looking to enhance your programming skills, this article will provide you with the insights you need to incorporate hidden text functionality into your applications.

## Prerequisites

Before diving into the coding part, there are a few prerequisites you need to take care of:

### Requirement Checklist
- Visual Studio: Make sure you have Visual Studio installed. This tutorial assumes you are using .NET Framework.
- Aspose.PDF for .NET: You need to have the Aspose.PDF for .NET library. You can download it [here](https://releases.aspose.com/pdf/net/).
- Basic knowledge of C#: Familiarity with C# programming will help you understand the code snippets better.

## Import Packages

Before you can get started with your code, you need to ensure you import the necessary Aspose.PDF namespaces. Here’s how to do it:

### Set Up Your Project
1. Open Visual Studio and create a new C# project or use an existing one.
2. Install Aspose.PDF by adding the NuGet package. You can do this by navigating to the NuGet Package Manager and searching for `Aspose.PDF`. 
3. Alternatively, you can directly download the library from [here](https://releases.aspose.com/pdf/net/) and add it as a reference in your project.

### Import Required Namespaces
At the top of your C# file, import the following namespaces:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

This step is crucial as these namespaces contain the classes and methods necessary to manipulate PDF documents.

## Creating a PDF Document with Hidden Text

Now that you’re set up, let’s go through the steps to create a PDF document that contains both visible and invisible text.

### Step 1: Define Document Directory
First, you'll want to set up the path where the PDF will be saved. This is where the magic begins!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Change this to your directory
```

This line defines where your generated PDF will be stored. Don’t forget to replace `YOUR DOCUMENT DIRECTORY` with your actual path.

### Step 2: Create a PDF Document
Next, let’s create a new PDF document and add pages to it.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Here, we're initializing a new document and adding a page where we will place our text fragments.

### Step 3: Add Visible and Hidden Text
Now we will add both visible and invisible text to our PDF.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

In this snippet, `frag1` will be visible, whereas `frag2` will be set to invisible next.

### Step 4: Set the Text to Invisible
To make the text of `frag2` invisible, you simply modify its `TextState`.

```csharp
frag2.TextState.Invisible = true;
```

By setting this property, any text associated with `frag2` will not be rendered when the PDF is viewed.

### Step 5: Add Text Fragments to Page
Finally, we add these text fragments to the page and save the PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

This part of the code adds our text fragments to the page. After that, we save and dispose of the document properly.

## Searching for Hidden Text in the PDF

Now that we've created our PDF with both visible and hidden text, how do we search for that hidden text? Let's break it down.

### Step 1: Load the PDF Document
To search for text within the PDF, we first need to load the document we just created.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Step 2: Create a Text Fragment Absorber
We will use `TextFragmentAbsorber` to capture all text fragments in the PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Here, we specify that we want to absorb all text fragments from the first page.

### Step 3: Iterate Through the Fragments
Now, we can iterate through the collected text fragments to find out which ones are visible and which are hidden.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

This loop checks each text fragment and prints out its contents along with its position and visibility status. If `fragment.TextState.Invisible` is set to true, it means that text is hidden!

### Step 4: Dispose of Document
Finally, remember to dispose of the document again once you're finished.

```csharp
doc.Dispose();
```

## Conclusion

In this tutorial, we walked through the exciting process of adding and searching for hidden text in PDF files using Aspose.PDF for .NET. We learned how to create a PDF document with both visible and hidden text, as well as how to search for that hidden text programmatically. This capability can be incredibly useful in various applications, whether you need to store confidential information or provide a unique user experience within your documents.

As you become more familiar with ASPose.PDF, the possibilities become endless. Keep experimenting and pushing the boundaries of what you can achieve with your PDF documents!

## FAQ's

### Can Aspose.PDF handle encrypted PDF files?  
Yes, Aspose.PDF supports encryption and decryption of PDF documents. You can easily secure your PDFs with passwords.

### Is there a trial version available for Aspose.PDF?  
Absolutely! You can download the free trial from [here](https://releases.aspose.com/).

### What programming languages does Aspose.PDF support?  
Aspose.PDF provides support for multiple languages, including C#, Java, and Python.

### Where can I find the documentation for Aspose.PDF?  
You can access the documentation [here](https://reference.aspose.com/pdf/net/).

### How can I get support if I encounter issues?  
For support, you can visit the Aspose forums [here](https://forum.aspose.com/c/pdf/10).
