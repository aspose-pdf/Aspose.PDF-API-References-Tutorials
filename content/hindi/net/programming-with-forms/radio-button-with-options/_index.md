---
title: विकल्पों के साथ रेडियो बटन
linktitle: विकल्पों के साथ रेडियो बटन
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके आसानी से PDF दस्तावेज़ में विकल्पों के साथ रेडियो बटन जोड़ें।
type: docs
weight: 230
url: /hi/net/programming-with-forms/radio-button-with-options/
---

इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में विकल्पों के साथ रेडियो बटन कैसे जोड़ें। हम इस प्रक्रिया में आपका मार्गदर्शन करने के लिए C# स्रोत कोड को चरण दर चरण समझाएँगे।

## चरण 1: तैयारी

सुनिश्चित करें कि आपने आवश्यक लाइब्रेरीज़ आयात कर ली हैं और अपने दस्तावेज़ निर्देशिका का पथ सेट कर लिया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ ऑब्जेक्ट को इंस्टैंसिएट करें

एक नया PDF दस्तावेज़ बनाने के लिए दस्तावेज़ ऑब्जेक्ट को इंस्टैंसिएट करें:

```csharp
Document doc = new Document();
```

## चरण 3: पृष्ठ और तालिका जोड़ें

दस्तावेज़ में एक पृष्ठ जोड़ें और रेडियो बटन विकल्प रखने के लिए एक तालिका बनाएं:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## चरण 4: रेडियोबटनफील्ड ऑब्जेक्ट को इंस्टैंसिएट करें

रेडियो बटन को दर्शाने के लिए रेडियोबटनफील्ड ऑब्जेक्ट को इंस्टैंसिएट करें:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## चरण 5: रेडियो बटन विकल्प जोड़ें

रेडियो बटन विकल्प को रेडियोबटनफील्ड ऑब्जेक्ट में जोड़ें:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## चरण 6: रेडियो बटन विकल्प अनुकूलित करें

बॉर्डर, टेक्स्ट रंग और कैप्शन टेक्स्ट जैसी विशेषताएं सेट करके रेडियो बटन विकल्पों को अनुकूलित करें:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// ऑप्ट2 और ऑप्ट3 के लिए समान चरणों को दोहराएं

```

## चरण 7: तालिका में रेडियो बटन विकल्प जोड़ें

उन्हें प्रदर्शित करने के लिए रेडियो बटन विकल्पों को तालिका में जोड़ें:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## चरण 8: पीडीएफ दस्तावेज़ सहेजें

निर्मित PDF दस्तावेज़ को सहेजें:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके विकल्पों के साथ रेडियो बटन के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// पीडीएफ फाइल को सेव करें
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में विकल्पों के साथ एक रेडियो बटन सफलतापूर्वक जोड़ लिया है। अब आप अपने PDF दस्तावेज़ों में इंटरैक्टिव फ़ॉर्म बनाने के लिए इस विधि का उपयोग कर सकते हैं।