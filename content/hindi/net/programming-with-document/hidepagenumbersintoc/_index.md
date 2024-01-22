---
title: टीओसी में पेज नंबर छुपाएं
linktitle: टीओसी में पेज नंबर छुपाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका से जानें कि .NET के लिए Aspose.PDF का उपयोग करके सामग्री तालिका में पृष्ठ संख्याओं को कैसे छिपाया जाए।
type: docs
weight: 220
url: /hi/net/programming-with-document/hidepagenumbersintoc/
---
इस लेख में, हम C# का उपयोग करके .NET के लिए Aspose.PDF के Hide Page Numbers In TOC फीचर के कार्यान्वयन पर चर्चा करेंगे। हम .NET के लिए Aspose.PDF के संक्षिप्त परिचय के साथ शुरुआत करेंगे और फिर इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका पर गौर करेंगे। 

## .NET के लिए Aspose.PDF का परिचय

.NET के लिए Aspose.PDF एक शक्तिशाली पीडीएफ हेरफेर घटक है जो डेवलपर्स को पीडीएफ फाइलों को प्रोग्रामेटिक रूप से बनाने, संपादित करने और हेरफेर करने की अनुमति देता है। यह सुविधाओं और कार्यात्मकताओं की एक विस्तृत श्रृंखला प्रदान करता है जो पीडीएफ दस्तावेज़ों के साथ काम करना आसान बनाता है। .NET के लिए Aspose.PDF 32-बिट और 64-बिट दोनों ऑपरेटिंग सिस्टम को सपोर्ट करता है और इसका उपयोग .NET फ्रेमवर्क, .NET कोर और Xamarin प्लेटफॉर्म के साथ किया जा सकता है। 

## TOC फीचर में पेज नंबर छुपाएं क्या है?

सामग्री तालिका (टीओसी) पीडीएफ दस्तावेज़ का एक अनिवार्य हिस्सा है जो उपयोगकर्ताओं को सामग्री का त्वरित अवलोकन प्रदान करता है। कभी-कभी, उपयोगकर्ता इसे अधिक उपयोगकर्ता-अनुकूल बनाने के लिए टीओसी में पेज नंबर छिपाना चाह सकते हैं। .NET के लिए Aspose.PDF TOC में पेज नंबर छिपाने के लिए एक अंतर्निहित सुविधा प्रदान करता है। इस सुविधा का उपयोग अधिक उपयोगकर्ता-अनुकूल पीडीएफ दस्तावेज़ बनाने के लिए किया जा सकता है। 

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, आपको निम्नलिखित की आवश्यकता होगी:

- विजुअल स्टूडियो 2010 या बाद का संस्करण
- आपके सिस्टम पर .NET के लिए Aspose.PDF स्थापित है
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान

## टीओसी सुविधा में पेज नंबर छुपाएं लागू करने के लिए चरण-दर-चरण मार्गदर्शिका

.NET के लिए Aspose.PDF का उपयोग करके TOC में पेज नंबर छुपाएं सुविधा को लागू करने के लिए नीचे दिए गए चरणों का पालन करें:

## चरण 1: विज़ुअल स्टूडियो में एक नया C# कंसोल एप्लिकेशन बनाएं

विज़ुअल स्टूडियो खोलें और एक नया C# कंसोल एप्लिकेशन बनाएं।

## चरण 2: .NET के लिए Aspose.PDF का संदर्भ जोड़ें

अपने प्रोजेक्ट में संदर्भ फ़ोल्डर पर राइट-क्लिक करें और संदर्भ जोड़ें चुनें। उस स्थान पर ब्राउज़ करें जहां आपके सिस्टम पर .NET के लिए Aspose.PDF स्थापित है और इसमें एक संदर्भ जोड़ें।

## चरण 1: एक नया पीडीएफ दस्तावेज़ बनाएं

निम्नलिखित कोड का उपयोग करके एक नया पीडीएफ दस्तावेज़ बनाएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## चरण 2: एक टीओसी पेज बनाएं

टीओसी के लिए एक नया पेज बनाएं और निम्नलिखित कोड का उपयोग करके इसे पीडीएफ दस्तावेज़ में जोड़ें:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## चरण 3: पीडीएफ दस्तावेज़ के अनुभाग संग्रह में सूची अनुभाग जोड़ें

निम्नलिखित कोड का उपयोग करके पीडीएफ दस्तावेज़ के अनुभाग संग्रह में सूची अनुभाग जोड़ें:

```csharp
tocPage.TocInfo = tocInfo;
```

## चरण 4: चार स्तरों की सूची के प्रारूप को परिभाषित करें

निम्नलिखित कोड का उपयोग करके प्रत्येक स्तर के बाएँ हाशिये और पाठ प्रारूप सेटिंग्स को सेट करके चार स्तरों की सूची के प्रारूप को परिभाषित करें:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## चरण 5: अनुभाग में चार शीर्षक जोड़ें

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### .NET के लिए Aspose.PDF का उपयोग करके TOC में पेज नंबर छिपाने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//पीडीएफ दस्तावेज़ के अनुभाग संग्रह में सूची अनुभाग जोड़ें
tocPage.TocInfo = tocInfo;
//बाएँ हाशिये को सेट करके चार स्तरों की सूची के प्रारूप को परिभाषित करें
//प्रत्येक स्तर की पाठ प्रारूप सेटिंग्स

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//अनुभाग में चार शीर्षक जोड़ें
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में XMP मेटाडेटा के साथ कैसे काम किया जाए। एक्सएमपी मेटाडेटा पीडीएफ दस्तावेज़ के बारे में बहुमूल्य जानकारी प्रदान करता है, जिसमें इसका शीर्षक, लेखक, निर्माण तिथि और बहुत कुछ शामिल है। .NET के लिए Aspose.PDF डेवलपर्स को इस मेटाडेटा तक पहुंचने और हेरफेर करने की अनुमति देता है, जो पीडीएफ दस्तावेजों के साथ काम करने के लिए एक लचीला और शक्तिशाली एपीआई प्रदान करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में एक्सएमपी मेटाडेटा क्या है?

उ: पीडीएफ दस्तावेज़ में एक्सएमपी (एक्स्टेंसिबल मेटाडेटा प्लेटफ़ॉर्म) मेटाडेटा दस्तावेज़ के बारे में मेटाडेटा जानकारी संग्रहीत करने के लिए एक मानक प्रारूप है। इसमें दस्तावेज़ का शीर्षक, लेखक, निर्माण तिथि, कीवर्ड और बहुत कुछ जैसे विवरण शामिल हैं। एक्सएमपी मेटाडेटा पीडीएफ दस्तावेज़ के बारे में जानकारी संग्रहीत और साझा करने का एक संरचित और मानकीकृत तरीका प्रदान करता है।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के XMP मेटाडेटा को संशोधित कर सकता हूँ?

 उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके किसी PDF दस्तावेज़ के XMP मेटाडेटा को प्रोग्रामेटिक रूप से संशोधित कर सकते हैं। आप तक पहुंच सकते हैं`Info` की संपत्ति`Document` ऑब्जेक्ट, जो आपको XMP मेटाडेटा गुणों तक पहुंच प्रदान करता है। फिर आप पीडीएफ दस्तावेज़ के एक्सएमपी मेटाडेटा को संशोधित करने के लिए इन गुणों के मूल्यों को अपडेट कर सकते हैं।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से कस्टम XMP मेटाडेटा गुण निकाल सकता हूँ?

 उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ से कस्टम XMP मेटाडेटा गुण निकाल सकते हैं। आप इसका उपयोग कर सकते हैं`Metadata` की संपत्ति`Document`ऑब्जेक्ट, जो पीडीएफ दस्तावेज़ के सभी एक्सएमपी मेटाडेटा गुणों तक पहुंच प्रदान करता है। फिर आप कस्टम गुण निकाल सकते हैं और आवश्यकतानुसार उनके मूल्यों का उपयोग कर सकते हैं।