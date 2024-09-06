---
title: रेडियो बटन कैप्शन सेट करें
linktitle: रेडियो बटन कैप्शन सेट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: PDF फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग करना सीखें।
type: docs
weight: 280
url: /hi/net/programming-with-forms/set-radio-button-caption/
---
इस गाइड में, हम चरण दर चरण बताएंगे कि PDF फॉर्म में रेडियो बटन के कैप्शन को परिभाषित करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। हम आपको दिखाएंगे कि रेडियो बटन फ़ील्ड तक कैसे पहुँचें, एक नया रेडियो बटन विकल्प कैसे बनाएँ और बटन कैप्शन को कस्टमाइज़ करें।

## चरण 1: दस्तावेज़ निर्देशिका को कॉन्फ़िगर करना

 पहला कदम उस डॉक्यूमेंट डायरेक्टरी को कॉन्फ़िगर करना है जहाँ वह पीडीएफ फॉर्म स्थित है जिस पर आप काम करना चाहते हैं। आप इसका उपयोग कर सकते हैं`dataDir` निर्देशिका पथ निर्दिष्ट करने के लिए चर.

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 2: स्रोत पीडीएफ फॉर्म लोड करना

 इस चरण में, हम स्रोत पीडीएफ फॉर्म को लोड करेंगे`Aspose.Pdf.Facades.Form` Aspose.PDF का वर्ग.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

सुनिश्चित करें कि फॉर्म वाली पीडीएफ फाइल निर्दिष्ट दस्तावेज़ निर्देशिका में मौजूद है।

## चरण 3: रेडियो बटन कैप्शन संपादित करना

हम फ़ॉर्म फ़ील्ड नामों के माध्यम से लूप करेंगे और रेडियो बटन फ़ील्ड की खोज करेंगे। यदि कोई मेल खाता फ़ील्ड मिलता है, तो हम कस्टम कैप्शन के साथ एक नया रेडियो बटन विकल्प बनाएंगे और इसे मौजूदा फ़ील्ड में जोड़ देंगे।

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
// TextParagraph ऑब्जेक्ट बनाएँ
TextParagraph par = new TextParagraph();
// पैराग्राफ़ स्थिति सेट करें
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// वर्ड रैप मोड निर्दिष्ट करें
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// पैराग्राफ़ में नया TextFragment जोड़ें
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

परिणामी PDF के लिए पूर्ण पथ और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन कैप्शन सेट करने के लिए नमूना स्रोत कोड 
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
		// टेक्स्टपैराग्राफ ऑब्जेक्ट बनाएँ
		TextParagraph par = new TextParagraph();
		// पैराग्राफ़ स्थिति सेट करें
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// शब्द रैपिंग मोड निर्दिष्ट करें
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// पैराग्राफ़ में नया टेक्स्टफ़्रेगमेंट जोड़ें
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

इस गाइड में, हमने सीखा कि PDF फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। वर्णित चरणों का पालन करके, आप रेडियो बटन विकल्पों को कस्टमाइज़ कर सकते हैं और आवश्यकतानुसार कैप्शन बदल सकते हैं। PDF फ़ाइलों में हेरफेर करने की संभावनाओं का विस्तार करने के लिए .NET के लिए Aspose.PDF की विशेषताओं को और अधिक जानने के लिए स्वतंत्र महसूस करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं PDF फॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकता हूं?

उत्तर: हाँ, आप PDF फ़ॉर्म में रेडियो बटन के लिए कैप्शन सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकते हैं। प्रदान किया गया नमूना स्रोत कोड दर्शाता है कि रेडियो बटन फ़ील्ड तक कैसे पहुँचें, कस्टम कैप्शन के साथ एक नया रेडियो बटन विकल्प कैसे बनाएँ और मौजूदा फ़ील्ड को कैसे अपडेट करें।

#### प्रश्न: मैं रेडियो बटन कैप्शन के स्वरूप को कैसे अनुकूलित कर सकता हूं, जैसे फ़ॉन्ट का आकार और रंग?

 उत्तर: आप रेडियो बटन कैप्शन के गुणों को समायोजित करके उसके स्वरूप को अनुकूलित कर सकते हैं।`TextFragment` कैप्शन के लिए उपयोग किया जाता है। उदाहरण के लिए, आप फ़ॉन्ट, फ़ॉन्ट आकार, रंग, लाइन स्पेसिंग और अन्य टेक्स्ट फ़ॉर्मेटिंग विकल्प सेट कर सकते हैं।

#### प्रश्न: क्या एक ही रेडियो बटन समूह में अलग-अलग कैप्शन वाले अनेक रेडियो बटन विकल्प जोड़ना संभव है?

उत्तर: हां, आप एक ही रेडियो बटन समूह में अलग-अलग कैप्शन के साथ कई रेडियो बटन विकल्प जोड़ सकते हैं। प्रत्येक विकल्प एक अलग विकल्प का प्रतिनिधित्व करेगा, और उपयोगकर्ता समूह से केवल एक विकल्प चुन सकते हैं।

#### प्रश्न: क्या मैं PDF दस्तावेज़ में अन्य फ़ॉर्म फ़ील्ड को संशोधित करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकता हूँ?

उत्तर: हाँ, .NET के लिए Aspose.PDF PDF दस्तावेज़ में विभिन्न फ़ॉर्म फ़ील्ड में हेरफेर करने के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है, जैसे कि टेक्स्ट फ़ील्ड, चेकबॉक्स, ड्रॉपडाउन सूचियाँ, और बहुत कुछ। आप मान सेट करने, दिखावट को संशोधित करने और फ़ॉर्म फ़ील्ड में अन्तरक्रियाशीलता जोड़ने के लिए लाइब्रेरी का उपयोग कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF अन्य स्रोतों से उत्पन्न PDFs, जैसे स्कैन किए गए दस्तावेज़ों के साथ काम करने का समर्थन करता है?

उत्तर: हां, .NET के लिए Aspose.PDF स्कैन किए गए दस्तावेज़ों सहित विभिन्न स्रोतों से उत्पन्न PDF के साथ काम करने का समर्थन करता है। लाइब्रेरी स्कैन किए गए PDF से टेक्स्ट निकालने और प्रोग्रामेटिक रूप से सामग्री में हेरफेर करने के लिए OCR (ऑप्टिकल कैरेक्टर रिकॉग्निशन) क्षमताएं प्रदान करती है।