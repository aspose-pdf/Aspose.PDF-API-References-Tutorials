---
title: Set Java Script
linktitle: Set Java Script
second_title: Aspose.PDF for .NET API Reference
description: Unlock the power of Aspose.PDF for .NET. Learn how to set up JavaScript on form fields with our step-by-step guide.
type: docs
weight: 270
url: /net/programming-with-forms/set-java-script/
---
## Introduction

Creating dynamic and interactive PDFs can significantly enhance user experience, especially when integrating forms and fields within a document. One powerful library that makes this possible is Aspose.PDF for .NET. In this article, we’ll dive deep into setting up JavaScript for form fields using Aspose.PDF, ensuring your PDFs not only look good but also function beautifully.

## Prerequisites

Before we jump into coding, let’s ensure you have everything you need to follow along smoothly:

- Visual Studio (or any .NET IDE): Make sure you have it installed and set up correctly.
  
- Aspose.PDF Library: You'll want the latest version of this library. You can download it [here](https://releases.aspose.com/pdf/net/).

- Basic Knowledge of C#: Familiarity with C# programming will help you better understand the code snippets.

- PDF Files: You should have a PDF file ready for testing. In our example, we’ll be using a file named `SetJavaScript.pdf`.

- Your Document Directory: Know where your document files are stored. We will reference this path in our code.

Once you have these prerequisites ready, which tools will we leverage? Let's explore what Aspose.PDF can do.

## Import Packages

To get started, you need to include the necessary namespaces in your C# project. Open your main C# file and add the following import statements:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

These namespaces provide access to the PDF and form-related functionality within the Aspose.PDF library.

Ready to make your PDF interactive? Grab your coding cap, and let’s break this down step-by-step!

## Step 1: Define the Document Path

First, we need to specify the location of our PDF file. This sets the stage for everything that follows. Here’s how you do it:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where your PDF file is located. Think of this as setting the coordinates for a treasure map—you need to know where the ‘X’ marks the spot!

## Step 2: Load the PDF Document

Once we’ve defined the directory, we’ll load our PDF file. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

This line opens your specified PDF file and prepares it for manipulation. 

## Step 3: Access the Form Field

Next, we want to access the form field where we’ll apply our JavaScript. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Here, we assume there's a text box in your PDF named `textbox1`. If you don’t have a field with this name, you can either rename it or adjust the code accordingly. 

## Step 4: Set Up JavaScript Actions

Now, let’s add some functionality to our text box! We will set up JavaScript actions that will be triggered on certain events. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Here’s what’s happening:
- OnModifyCharacter: This JavaScript function specifies how the field should behave when a character is modified. In this case, it allows two decimal points after the number with no separator.
- OnFormat: This ensures that when the user formats the number, it adheres to the same rule.

By setting up these actions, we're essentially giving our text box a personality—like teaching it a dance move!

## Step 5: Initialize the Field Value

Next, let’s give our text box a starting point by setting an initial value. 

```csharp
field.Value = "123";
```

This line sets "123" as the pre-filled value in the text box. It’s like prepping a stage for a performance.

## Step 6: Save the Modified PDF

Finally, we need to save our document after making all these changes.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

This updates the original file with your changes and saves it as `Restricted_out.pdf`. Think of this as sealing the fate of our PDF—once saved, it’s ready for the world!

## Step 7: Confirm Success

Lastly, let’s check if everything went smoothly. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Running this message will reassure you that the operation has completed successfully, just like receiving a clap from the audience after a great performance.

## Conclusion

Congratulations! You’ve successfully set up JavaScript for form fields in a PDF using Aspose.PDF for .NET. This tutorial not only gave you the tools to enhance user interaction but also empowered you to personalize your documents like a pro. Whether you're working with forms in invoices, surveys, or other interactive PDFs, the possibilities are truly endless.

### FAQ's

### What is Aspose.PDF for .NET?  
Aspose.PDF is a library designed to create, edit, and manipulate PDF files within .NET applications, providing powerful PDF functionalities.

### Do I need a license to use Aspose.PDF?  
While a free trial is available, a license is required for full usage without limitations. You can purchase a license [here](https://purchase.aspose.com/buy).

### Can I set JavaScript on other types of form fields?  
Absolutely! Aspose.PDF allows JavaScript actions on various form fields such as checkboxes, radio buttons, and dropdowns.

### How can I get support for Aspose.PDF issues?  
You can access support through their [forum](https://forum.aspose.com/c/pdf/10) for any queries or issues.

### Is there a way to test Aspose.PDF without purchasing?  
Yes! Aspose provides a [free trial](https://releases.aspose.com/) to test the library’s features before committing to a purchase.
