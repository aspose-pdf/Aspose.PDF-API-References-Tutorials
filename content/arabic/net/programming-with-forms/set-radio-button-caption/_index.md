---
title: Set Radio Button Caption
linktitle: Set Radio Button Caption
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to set the caption for a radio button in a PDF form.
type: docs
weight: 280
url: /ar/net/programming-with-forms/set-radio-button-caption/
---
In this guide, we will explain step by step how to use the Aspose.PDF library for .NET to define the caption of a radio button in a PDF form. We'll show you how to access the radio button field, create a new radio button option, and customize the button caption.

## Step 1: Configuring the document directory

The first step is to configure the document directory where the PDF form you want to work on is located. You can use the `dataDir` variable to specify the directory path.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to your documents directory.

## Step 2: Loading the source PDF form

In this step, we will load the source PDF form using the `Aspose.Pdf.Facades.Form` class of Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Make sure that the PDF file containing the form is present in the specified documents directory.

## Step 3: Editing the radio button caption

We'll loop through the form field names and search for radio button fields. If a matching field is found, we'll create a new radio button option with a custom caption and add it to the existing field.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Create a TextParagraph object
TextParagraph par = new TextParagraph();
// Set paragraph position
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Specify word wrap mode
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Add the new TextFragment to the paragraph
par.AppendLine(updatedFragment);
// Add the TextParagraph using TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Customize the caption radio button and other settings as needed.

## Step 4: Saving the Resulting PDF

Now that we are done modifying the radio button caption, we can save the resulting PDF using the `Save` method of the `Document` class.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Be sure to specify the full path and filename for the resulting PDF.

### Sample source code for Set Radio Button Caption using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load source PDF form
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Create TextParagraph object
		TextParagraph par = new TextParagraph();
		// Set paragraph position
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Specify word wraping mode
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Add new TextFragment to paragraph
		par.AppendLine(updatedFragment);
		// Add the TextParagraph using TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusion

In this guide, we learned how to use the Aspose.PDF library for .NET to set the caption for a radio button in a PDF form. By following the described steps, you can customize the radio button options and change the caption as needed. Feel free to further explore the features of Aspose.PDF for .NET to expand the possibilities of manipulating PDF files.

### FAQ's

#### Q: Can I use Aspose.PDF for .NET to set captions for radio buttons in a PDF form?

A: Yes, you can use Aspose.PDF for .NET to set captions for radio buttons in a PDF form. The provided sample source code demonstrates how to access the radio button field, create a new radio button option with a custom caption, and update the existing field.

#### Q: How can I customize the appearance of the radio button caption, such as font size and color?

A: You can customize the appearance of the radio button caption by adjusting the properties of the `TextFragment` used for the caption. For example, you can set the font, font size, color, line spacing, and other text formatting options.

#### Q: Is it possible to add multiple radio button options with different captions to a single radio button group?

A: Yes, you can add multiple radio button options with different captions to a single radio button group. Each option will represent a different choice, and users can select only one option from the group.

#### Q: Can I use Aspose.PDF for .NET to modify other form fields in a PDF document?

A: Yes, Aspose.PDF for .NET provides a comprehensive set of features to manipulate various form fields in a PDF document, such as text fields, checkboxes, dropdown lists, and more. You can use the library to set values, modify appearances, and add interactivity to form fields.

#### Q: Does Aspose.PDF for .NET support working with PDFs generated from other sources, such as scanned documents?

A: Yes, Aspose.PDF for .NET supports working with PDFs generated from various sources, including scanned documents. The library provides OCR (Optical Character Recognition) capabilities to extract text from scanned PDFs and manipulate the content programmatically.