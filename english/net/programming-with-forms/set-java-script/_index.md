---
title: Set Java Script
linktitle: Set Java Script
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to set JavaScript in form fields in PDF files.
type: docs
weight: 270
url: /net/programming-with-forms/set-java-script/
---
In this guide, we are going to explain step by step how to use the Aspose.PDF library for .NET to define JavaScript in a form field of a PDF document. We'll show you how to configure JavaScript actions to perform specific operations on the text field.

## Prerequisites

Before you begin, make sure you have the following:

- A .NET development environment installed on your system.
- The Aspose.PDF library for .NET. You can download it from Aspose official website.

## Step 1: Configuring the document directory

The first step is to configure the document directory where the PDF file you want to work on is located. You can use the `dataDir` variable to specify the directory path.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to your documents directory.

## Step 2: Loading the input PDF file

In this step, we will load the input PDF file using the `Document` class of Aspose.PDF.

```csharp
// Load input PDF file
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Make sure that the input PDF file is present in the specified documents directory.

## Step 3: Accessing the TextBox field

To apply JavaScript to a specific text field, we first need to access that field. In this example, we assume the text field is called "textbox1". Use the `doc.Form["textbox1"]` method to get the corresponding `TextBoxField` object.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Make sure the specified text field exists in the input PDF file.

## Step 4: Configure JavaScript actions

Now that we have accessed the text field, we can configure the JavaScript actions associated with this field. In this example, we will use two actions: `OnModifyCharacter` and `OnFormat`. These actions will be defined using `JavascriptAction` objects.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Be sure to customize the JavaScript actions according to your needs.

## Step 5: Setting the initial field value

Before saving the resulting PDF, we can set an initial value for the text field. In this example, we will set the value "123" for the field.

```csharp
field.Value = "123";
```

Customize this value according to your needs.

## Step 6: Saving the Resulting PDF

Now that we are done setting up the text field and JavaScript actions, we can save the resulting PDF using the `Save` method of the `Document` class.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Save resulting PDF
doc.Save(dataDir);
```

Be sure to specify the full path and filename for the resulting PDF.


### Sample source code for Set Java Script using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load input PDF file
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 digits after point
// No separator
// Neg style = minus
// No currency
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Set initial field value
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Save resultant PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this guide, we learned how to use the Aspose.PDF library for .NET to set JavaScript in a form field of a PDF document. By following the steps outlined, you can customize JavaScript actions to perform various operations on text fields. Feel free to further explore the features of Aspose.PDF for .NET to expand the possibilities of manipulating PDF files.


### FAQ's

#### Q: Can I use Aspose.PDF for .NET to add JavaScript to other form elements, such as checkboxes and radio buttons?

A: Yes, Aspose.PDF for .NET allows you to add JavaScript to various form elements, including checkboxes, radio buttons, and dropdown lists. You can use the `JavascriptAction` class to define JavaScript actions for different form elements.

#### Q: Is it possible to validate user input using JavaScript in form fields?

A: Yes, you can use JavaScript to validate user input in form fields. By defining JavaScript actions like `OnBlur` or `OnKeystroke` for a form field, you can validate the entered data and display error messages if necessary.

#### Q: Can I execute complex JavaScript functions using Aspose.PDF for .NET?

A: Yes, you can execute complex JavaScript functions using Aspose.PDF for .NET. You have the flexibility to define custom JavaScript functions and call them within the `JavascriptAction`.

#### Q: Does Aspose.PDF for .NET support JavaScript events other than those mentioned in this tutorial?

A: Yes, Aspose.PDF for .NET supports a wide range of JavaScript events, including `OnMouseEnter`, `OnMouseExit`, `OnMouseDown`, and `OnMouseUp`, among others. You can use these events to trigger JavaScript actions based on user interactions.

#### Q: Can I use Aspose.PDF for .NET to extract JavaScript code from existing PDF documents?

A: Aspose.PDF for .NET provides the ability to extract JavaScript code from existing PDF documents. You can use the `JavascriptAction` class and other relevant methods to access and analyze JavaScript actions in a PDF form.
