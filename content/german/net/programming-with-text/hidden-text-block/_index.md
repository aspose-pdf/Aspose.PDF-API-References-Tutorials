---
title: Hidden Text Block In PDF File
linktitle: Hidden Text Block In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create hidden text blocks in PDF file using Aspose.PDF for .NET.
type: docs
weight: 230
url: /de/net/programming-with-text/hidden-text-block/
---
In this tutorial, we will explain how to create a hidden text block in PDF file using the Aspose.PDF library for .NET. A hidden text block is a floating text that becomes visible when the mouse cursor hovers over a specific area. We will go through the step-by-step process of creating the hidden text block using the provided C# source code.

## Requirements

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where you want to save the generated PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your desired directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Sample Document

In this step, we create a sample PDF document and add a text fragment to it. The text fragment will serve as the trigger for displaying the hidden text block.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Step 3: Open the Document

Now, we open the previously created document using the `Document` class.

```csharp
Document document = new Document(outputFile);
```

## Step 4: Find the Text Fragment

We use a `TextFragmentAbsorber` object to find the text fragment that will trigger the display of the hidden text block. In this case, we are searching for the exact text "Move the mouse cursor here to display floating text".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Step 5: Create the Hidden Text Field

We create a `TextBoxField` object to represent the hidden text field. This field will contain the text that becomes visible when the mouse cursor hovers over the trigger text.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Step 6: Add the Hidden Text Field to the Document

We add the hidden text field to the document's form collection.

```csharp
document.Form.Add(floatingField);
```

## Step 7: Create the Invisible Button

We create an invisible button field that will be positioned on top of the trigger text fragment. This button field will have actions associated with mouse enter and exit events.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Step 8: Save the Document

Finally, we save the modified document with the hidden text block.

```csharp
document. Save(outputFile);
```

### Sample source code for Hidden Text Block using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Create sample document with text
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Open document with text
Document document = new Document(outputFile);
// Create TextAbsorber object to find all the phrases matching the regular expression
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Accept the absorber for the document pages
document.Pages.Accept(absorber);
// Get the first extracted text fragment
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Create hidden text field for floating text in the specified rectangle of the page
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Set text to be displayed as field value
floatingField.Value = "This is the \"floating text field\".";
// We recommend to make field 'readonly' for this scenario
floatingField.ReadOnly = true;
// Set 'hidden' flag to make field invisible on document opening
floatingField.Flags |= AnnotationFlags.Hidden;
// Setting a unique field name isn't necessary but allowed
floatingField.PartialName = "FloatingField_1";
// Setting characteristics of field appearance isn't necessary but makes it better
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Add text field to the document
document.Form.Add(floatingField);
// Create invisible button on text fragment position
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Create new hide action for specified field (annotation) and invisibility flag.
// (You also may reffer floating field by the name if you specified it above.)
// Add actions on mouse enter/exit at the invisible button field
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Add button field to the document
document.Form.Add(buttonField);
// Save document
document.Save(outputFile);
```

## Conclusion

In this tutorial, you have learned how to create a hidden text block using the Aspose.PDF for .NET library. By following the step-by-step guide, you can generate a PDF document with a hidden text field that becomes visible when the mouse cursor hovers over a specific area. You can customize the appearance and behavior of the hidden text block according to your requirements.

### FAQ's

#### Q: What is the purpose of the "Hidden Text Block In PDF File" tutorial?

A: The "Hidden Text Block In PDF File" tutorial explains how to create a hidden text block in a PDF file using the Aspose.PDF library for .NET. A hidden text block is a floating text that becomes visible when the mouse cursor hovers over a specific area. This tutorial provides a step-by-step guide using C# source code.

#### Q: Why would I want to create a hidden text block in a PDF file?

A: Creating a hidden text block can be useful for interactive PDF documents where you want to provide additional information or context that only becomes visible when a user hovers their mouse cursor over a designated area.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where you want to save the generated PDF file.

#### Q: How do I create a sample document and add a text fragment to it?

A: In the tutorial, you use the `Document` class to create a sample PDF document and add a text fragment. This text fragment serves as the trigger for displaying the hidden text block.

#### Q: How do I find the text fragment that triggers the hidden text block?

A: The tutorial demonstrates how to use a `TextFragmentAbsorber` object to find the text fragment that triggers the display of the hidden text block. It searches for a specific text string within the PDF document.

#### Q: How do I create and customize the hidden text field?

A: You create a `TextBoxField` object to represent the hidden text field. The tutorial provides code to set various properties such as position, value, appearance, and behavior of the hidden text field.

#### Q: How do I create an invisible button associated with the hidden text block?

A: An invisible button field is created using the `ButtonField` class. This button field is positioned on top of the trigger text fragment and has actions associated with mouse enter and exit events. These actions control the visibility of the hidden text block.

#### Q: Can I customize the appearance of the hidden text block and the trigger area?

A: Yes, you can customize various properties of both the hidden text field and the invisible button, including font, color, size, and positioning.

#### Q: How do I save the modified document with the hidden text block?

A: The tutorial demonstrates how to save the modified document using the `Save` method of the `Document` class.