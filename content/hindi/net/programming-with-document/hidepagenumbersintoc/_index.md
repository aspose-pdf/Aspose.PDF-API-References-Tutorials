---
title: TOC में पृष्ठ संख्या छिपाएँ
linktitle: TOC में पृष्ठ संख्या छिपाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.PDF का उपयोग करके सामग्री तालिका में पृष्ठ संख्याओं को छिपाने का तरीका जानें।
type: docs
weight: 220
url: /hi/net/programming-with-document/hidepagenumbersintoc/
---
इस लेख में, हम C# का उपयोग करके .NET के लिए Aspose.PDF की TOC में पेज नंबर छिपाने की सुविधा के कार्यान्वयन पर चर्चा करेंगे। हम .NET के लिए Aspose.PDF के संक्षिप्त परिचय के साथ शुरू करेंगे और फिर इस सुविधा को लागू करने के लिए चरण-दर-चरण मार्गदर्शिका में गोता लगाएँगे। 

## .NET के लिए Aspose.PDF का परिचय

Aspose.PDF for .NET एक शक्तिशाली PDF मैनिपुलेशन घटक है जो डेवलपर्स को प्रोग्रामेटिक रूप से PDF फ़ाइलें बनाने, संपादित करने और उनमें हेरफेर करने की अनुमति देता है। यह कई प्रकार की सुविधाएँ और कार्यक्षमताएँ प्रदान करता है जो PDF दस्तावेज़ों के साथ काम करना आसान बनाते हैं। Aspose.PDF for .NET 32-बिट और 64-बिट दोनों ऑपरेटिंग सिस्टम का समर्थन करता है और इसका उपयोग .NET Framework, .NET Core और Xamarin प्लेटफ़ॉर्म के साथ किया जा सकता है। 

## TOC में पृष्ठ संख्या छिपाने की सुविधा क्या है?

सामग्री की तालिका (TOC) एक PDF दस्तावेज़ का एक अनिवार्य हिस्सा है जो उपयोगकर्ताओं को सामग्री का त्वरित अवलोकन प्रदान करता है। कभी-कभी, उपयोगकर्ता इसे अधिक उपयोगकर्ता-अनुकूल बनाने के लिए TOC में पृष्ठ संख्याएँ छिपाना चाह सकते हैं। .NET के लिए Aspose.PDF TOC में पृष्ठ संख्याएँ छिपाने के लिए एक अंतर्निहित सुविधा प्रदान करता है। इस सुविधा का उपयोग अधिक उपयोगकर्ता-अनुकूल PDF दस्तावेज़ बनाने के लिए किया जा सकता है। 

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए आपको निम्नलिखित की आवश्यकता होगी:

- Visual Studio 2010 या बाद का संस्करण
- आपके सिस्टम पर .NET के लिए Aspose.PDF स्थापित है
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान

## TOC में पृष्ठ संख्या छिपाने की सुविधा को क्रियान्वित करने के लिए चरण-दर-चरण मार्गदर्शिका

.NET के लिए Aspose.PDF का उपयोग करके TOC में पृष्ठ संख्या छिपाने की सुविधा को लागू करने के लिए नीचे दिए गए चरणों का पालन करें:

## चरण 1: Visual Studio में एक नया C# कंसोल अनुप्रयोग बनाएँ

विज़ुअल स्टूडियो खोलें और एक नया C# कंसोल अनुप्रयोग बनाएं।

## चरण 2: .NET के लिए Aspose.PDF में संदर्भ जोड़ें

अपने प्रोजेक्ट में संदर्भ फ़ोल्डर पर राइट-क्लिक करें और संदर्भ जोड़ें चुनें। उस स्थान पर ब्राउज़ करें जहाँ आपके सिस्टम पर Aspose.PDF for .NET स्थापित है और उसमें संदर्भ जोड़ें।

## चरण 1: एक नया PDF दस्तावेज़ बनाएँ

निम्नलिखित कोड का उपयोग करके एक नया PDF दस्तावेज़ बनाएं:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## चरण 2: TOC पृष्ठ बनाएँ

TOC के लिए एक नया पृष्ठ बनाएं और निम्नलिखित कोड का उपयोग करके इसे PDF दस्तावेज़ में जोड़ें:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## चरण 3: पीडीएफ दस्तावेज़ के अनुभाग संग्रह में सूची अनुभाग जोड़ें

निम्नलिखित कोड का उपयोग करके PDF दस्तावेज़ के अनुभाग संग्रह में सूची अनुभाग जोड़ें:

```csharp
tocPage.TocInfo = tocInfo;
```

## चरण 4: चार स्तरों की सूची का प्रारूप निर्धारित करें

निम्नलिखित कोड का उपयोग करके प्रत्येक स्तर के बाएं मार्जिन और पाठ प्रारूप सेटिंग्स को सेट करके चार स्तरों की सूची का प्रारूप परिभाषित करें:

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

### .NET के लिए Aspose.PDF का उपयोग करके TOC में पृष्ठ संख्या छिपाने के लिए उदाहरण स्रोत कोड

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
//बाएँ मार्जिन और चिह्न सेट करके चार स्तरों की सूची का प्रारूप निर्धारित करें
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

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में XMP मेटाडेटा के साथ काम करने का तरीका खोजा। XMP मेटाडेटा PDF दस्तावेज़ के बारे में मूल्यवान जानकारी प्रदान करता है, जिसमें उसका शीर्षक, लेखक, निर्माण तिथि और बहुत कुछ शामिल है। .NET के लिए Aspose.PDF डेवलपर्स को इस मेटाडेटा तक पहुँचने और उसमें हेरफेर करने की अनुमति देता है, जो PDF दस्तावेज़ों के साथ काम करने के लिए एक लचीला और शक्तिशाली API प्रदान करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: PDF दस्तावेज़ में XMP मेटाडेटा क्या है?

उत्तर: PDF दस्तावेज़ में XMP (एक्सटेंसिबल मेटाडेटा प्लेटफ़ॉर्म) मेटाडेटा दस्तावेज़ के बारे में मेटाडेटा जानकारी संग्रहीत करने के लिए एक मानक प्रारूप है। इसमें दस्तावेज़ का शीर्षक, लेखक, निर्माण तिथि, कीवर्ड और बहुत कुछ जैसे विवरण शामिल हैं। XMP मेटाडेटा PDF दस्तावेज़ के बारे में जानकारी संग्रहीत करने और साझा करने का एक संरचित और मानकीकृत तरीका प्रदान करता है।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के XMP मेटाडेटा को संशोधित कर सकता हूँ?

 उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके प्रोग्रामेटिक रूप से PDF दस्तावेज़ के XMP मेटाडेटा को संशोधित कर सकते हैं। आप एक्सेस कर सकते हैं`Info` की संपत्ति`Document` ऑब्जेक्ट, जो आपको XMP मेटाडेटा गुणों तक पहुँच प्रदान करता है। फिर आप PDF दस्तावेज़ के XMP मेटाडेटा को संशोधित करने के लिए इन गुणों के मानों को अपडेट कर सकते हैं।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से कस्टम XMP मेटाडेटा गुण निकाल सकता हूँ?

 उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से कस्टम XMP मेटाडेटा गुण निकाल सकते हैं। आप इसका उपयोग कर सकते हैं`Metadata` की संपत्ति`Document`ऑब्जेक्ट, जो PDF दस्तावेज़ के सभी XMP मेटाडेटा गुणों तक पहुँच प्रदान करता है। फिर आप कस्टम गुण निकाल सकते हैं और आवश्यकतानुसार उनके मानों का उपयोग कर सकते हैं।