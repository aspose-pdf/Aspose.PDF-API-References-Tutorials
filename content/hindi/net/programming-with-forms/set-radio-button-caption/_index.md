---
title: रेडियो बटन कैप्शन सेट करें
linktitle: रेडियो बटन कैप्शन सेट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: पीडीएफ फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग करना सीखें।
type: docs
weight: 280
url: /hi/net/programming-with-forms/set-radio-button-caption/
---
इस गाइड में, हम चरण दर चरण बताएंगे कि रेडियो बटन के कैप्शन को पीडीएफ फॉर्म में परिभाषित करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। हम आपको दिखाएंगे कि रेडियो बटन फ़ील्ड तक कैसे पहुंचें, एक नया रेडियो बटन विकल्प कैसे बनाएं और बटन कैप्शन को कस्टमाइज़ करें।

## चरण 1: दस्तावेज़ निर्देशिका को कॉन्फ़िगर करना

 पहला कदम दस्तावेज़ निर्देशिका को कॉन्फ़िगर करना है जहां पीडीएफ फॉर्म जिस पर आप काम करना चाहते हैं वह स्थित है। आप इसका उपयोग कर सकते हैं`dataDir` निर्देशिका पथ निर्दिष्ट करने के लिए चर।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 2: स्रोत पीडीएफ फॉर्म लोड हो रहा है

 इस चरण में, हम इसका उपयोग करके स्रोत पीडीएफ फॉर्म लोड करेंगे`Aspose.Pdf.Facades.Form` Aspose.PDF की कक्षा।

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

सुनिश्चित करें कि फॉर्म वाली पीडीएफ फाइल निर्दिष्ट दस्तावेज़ निर्देशिका में मौजूद है।

## चरण 3: रेडियो बटन कैप्शन संपादित करना

हम प्रपत्र फ़ील्ड नामों के माध्यम से लूप करेंगे और रेडियो बटन फ़ील्ड की खोज करेंगे। यदि कोई मेल खाने वाला फ़ील्ड मिलता है, तो हम कस्टम कैप्शन के साथ एक नया रेडियो बटन विकल्प बनाएंगे और इसे मौजूदा फ़ील्ड में जोड़ देंगे।

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
// एक टेक्स्टपैराग्राफ ऑब्जेक्ट बनाएं
TextParagraph par = new TextParagraph();
// अनुच्छेद स्थिति निर्धारित करें
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// वर्ड रैप मोड निर्दिष्ट करें
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// पैराग्राफ में नया टेक्स्टफ़्रैगमेंट जोड़ें
par.AppendLine(updatedFragment);
// TextBuilder का उपयोग करके TextParagraph जोड़ें
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

आवश्यकतानुसार कैप्शन रेडियो बटन और अन्य सेटिंग्स को अनुकूलित करें।

## चरण 4: परिणामी पीडीएफ को सहेजना

 अब जब हमने रेडियो बटन कैप्शन को संशोधित कर लिया है, तो हम परिणामी पीडीएफ को इसका उपयोग करके सहेज सकते हैं`Save` की विधि`Document` कक्षा।

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

परिणामी पीडीएफ के लिए पूर्ण पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.PDF का उपयोग करके सेट रेडियो बटन कैप्शन के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// स्रोत पीडीएफ फॉर्म लोड करें
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
		// टेक्स्टपैराग्राफ ऑब्जेक्ट बनाएं
		TextParagraph par = new TextParagraph();
		// अनुच्छेद स्थिति निर्धारित करें
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// वर्ड रैपिंग मोड निर्दिष्ट करें
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// पैराग्राफ में नया टेक्स्टफ़्रैगमेंट जोड़ें
		par.AppendLine(updatedFragment);
		// TextBuilder का उपयोग करके TextParagraph जोड़ें
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## निष्कर्ष

इस गाइड में, हमने सीखा कि पीडीएफ फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। वर्णित चरणों का पालन करके, आप रेडियो बटन विकल्पों को अनुकूलित कर सकते हैं और आवश्यकतानुसार कैप्शन बदल सकते हैं। पीडीएफ फाइलों में हेरफेर करने की संभावनाओं का विस्तार करने के लिए .NET के लिए Aspose.PDF की सुविधाओं का और अधिक पता लगाने के लिए स्वतंत्र महसूस करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं पीडीएफ फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकता हूं?

उ: हां, आप पीडीएफ फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकते हैं। प्रदान किया गया नमूना स्रोत कोड दर्शाता है कि रेडियो बटन फ़ील्ड तक कैसे पहुंचें, कस्टम कैप्शन के साथ एक नया रेडियो बटन विकल्प कैसे बनाएं और मौजूदा फ़ील्ड को अपडेट करें।

#### प्रश्न: मैं रेडियो बटन कैप्शन की उपस्थिति, जैसे फ़ॉन्ट आकार और रंग, को कैसे अनुकूलित कर सकता हूं?

 उ: आप रेडियो बटन कैप्शन के गुणों को समायोजित करके उसके स्वरूप को अनुकूलित कर सकते हैं`TextFragment` कैप्शन के लिए उपयोग किया जाता है। उदाहरण के लिए, आप फ़ॉन्ट, फ़ॉन्ट आकार, रंग, पंक्ति रिक्ति और अन्य टेक्स्ट फ़ॉर्मेटिंग विकल्प सेट कर सकते हैं।

#### प्रश्न: क्या एक ही रेडियो बटन समूह में विभिन्न कैप्शन के साथ कई रेडियो बटन विकल्प जोड़ना संभव है?

उ: हां, आप एक ही रेडियो बटन समूह में विभिन्न कैप्शन के साथ कई रेडियो बटन विकल्प जोड़ सकते हैं। प्रत्येक विकल्प एक अलग विकल्प का प्रतिनिधित्व करेगा, और उपयोगकर्ता समूह से केवल एक विकल्प का चयन कर सकते हैं।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में अन्य फॉर्म फ़ील्ड को संशोधित करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकता हूं?

उत्तर: हां, .NET के लिए Aspose.PDF एक पीडीएफ दस्तावेज़ में विभिन्न फॉर्म फ़ील्ड, जैसे टेक्स्ट फ़ील्ड, चेकबॉक्स, ड्रॉपडाउन सूचियां और बहुत कुछ में हेरफेर करने के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है। आप मान सेट करने, दिखावे को संशोधित करने और फॉर्म फ़ील्ड में इंटरैक्टिविटी जोड़ने के लिए लाइब्रेरी का उपयोग कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF अन्य स्रोतों, जैसे स्कैन किए गए दस्तावेज़ों से उत्पन्न पीडीएफ के साथ काम करने का समर्थन करता है?

उत्तर: हाँ, .NET के लिए Aspose.PDF स्कैन किए गए दस्तावेज़ों सहित विभिन्न स्रोतों से उत्पन्न PDF के साथ काम करने का समर्थन करता है। लाइब्रेरी स्कैन किए गए पीडीएफ से टेक्स्ट निकालने और सामग्री को प्रोग्रामेटिक रूप से हेरफेर करने के लिए ओसीआर (ऑप्टिकल कैरेक्टर रिकग्निशन) क्षमताएं प्रदान करती है।