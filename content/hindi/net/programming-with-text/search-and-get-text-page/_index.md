---
title: पीडीएफ फाइल में टेक्स्ट पेज खोजें और प्राप्त करें
linktitle: पीडीएफ फाइल में टेक्स्ट पेज खोजें और प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में किसी विशिष्ट पृष्ठ से पाठ खोजना और प्राप्त करना सीखें।
type: docs
weight: 430
url: /hi/net/programming-with-text/search-and-get-text-page/
---
यह ट्यूटोरियल बताता है कि PDF फ़ाइल में किसी विशिष्ट पृष्ठ से टेक्स्ट खोजने और प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

## आवश्यक शर्तें

ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित है। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या अपने प्रोजेक्ट में इसे स्थापित करने के लिए NuGet का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें

अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाकर आरंभ करें और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें

आवश्यक नामस्थानों को आयात करने के लिए अपनी C# फ़ाइल के आरंभ में निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: पीडीएफ दस्तावेज़ लोड करें

 अपने PDF दस्तावेज़ निर्देशिका का पथ सेट करें और इसका उपयोग करके दस्तावेज़ लोड करें`Document` कक्षा:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 4: किसी पृष्ठ से पाठ खोजें और निकालें

 एक बनाने के`TextFragmentAbsorber`किसी विशिष्ट पृष्ठ पर इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए ऑब्जेक्ट:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 प्रतिस्थापित करें`"Figure"` उस वास्तविक पाठ के साथ जिसे आप खोजना चाहते हैं.

## चरण 5: किसी विशिष्ट पृष्ठ पर खोजें

दस्तावेज़ के किसी विशिष्ट पृष्ठ के लिए अवशोषक स्वीकार करें:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## चरण 6: निकाले गए पाठ अंश प्राप्त करें

का उपयोग करके निकाले गए पाठ अंश प्राप्त करें`TextFragments` की संपत्ति`TextFragmentAbsorber` वस्तु:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## चरण 7: पाठ के टुकड़ों और खंडों के माध्यम से लूप करें

getd पाठ अंशों और उनके खंडों के माध्यम से लूप करें, और उनके गुणों तक पहुँचें:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

आप प्रत्येक पाठ खंड पर आगे की क्रियाएं करने के लिए लूप के भीतर कोड को संशोधित कर सकते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके खोज और पाठ पृष्ठ प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएँ
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages.Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के किसी विशिष्ट पृष्ठ से टेक्स्ट कैसे खोजें और प्राप्त करें। इस ट्यूटोरियल ने दस्तावेज़ को लोड करने से लेकर निकाले गए टेक्स्ट सेगमेंट तक पहुँचने तक चरण-दर-चरण मार्गदर्शन प्रदान किया है। अब आप शामिल कर सकते हैं

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "खोजें और टेक्स्ट पृष्ठ प्राप्त करें" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "खोजें और टेक्स्ट पेज प्राप्त करें" ट्यूटोरियल को यह दिखाने के लिए डिज़ाइन किया गया है कि PDF फ़ाइल के भीतर किसी विशिष्ट पृष्ठ से टेक्स्ट खोजने और प्राप्त करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल प्रक्रिया को प्रदर्शित करने के लिए विस्तृत निर्देश और नमूना C# कोड प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में किसी विशिष्ट पृष्ठ से पाठ निकालने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल आपको Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ के किसी विशेष पृष्ठ से टेक्स्ट निकालने की प्रक्रिया के बारे में बताता है। यह आवश्यक चरणों की रूपरेखा बताता है और चयनित पृष्ठ पर निर्दिष्ट टेक्स्ट वाक्यांश की खोज करने और संबंधित टेक्स्ट खंडों को पुनः प्राप्त करने के लिए C# कोड प्रदान करता है।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए पूर्वापेक्षाएँ क्या हैं?

उत्तर: इस ट्यूटोरियल को शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपके पास .NET लाइब्रेरी के लिए Aspose.PDF स्थापित होना चाहिए। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में एकीकृत करने के लिए NuGet का उपयोग कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उत्तर: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। इससे आप अपनी परियोजना में लाइब्रेरी की क्षमताओं का उपयोग कर पाएँगे।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ के किसी विशिष्ट पृष्ठ पर पाठ खोज सकता हूँ?

उत्तर: हां, यह ट्यूटोरियल दर्शाता है कि पीडीएफ दस्तावेज़ के किसी विशिष्ट पृष्ठ पर टेक्स्ट कैसे खोजा जाए। इसमें उपयोग करना शामिल है`TextFragmentAbsorber` चुने हुए पृष्ठ पर किसी विशेष पाठ वाक्यांश के उदाहरणों का पता लगाने के लिए क्लास का उपयोग करें।

#### प्रश्न: मैं विशिष्ट पृष्ठ से निकाले गए पाठ खंडों तक कैसे पहुंच सकता हूं?

 उत्तर: निर्दिष्ट पृष्ठ पर पाठ खोजने के बाद, आप निकाले गए पाठ खंडों तक पहुंच सकते हैं`TextSegments` की संपत्ति`TextFragment` ऑब्जेक्ट. यह प्रॉपर्टी संग्रह तक पहुंच प्रदान करती है`TextSegment` वे ऑब्जेक्ट जिनमें निकाला गया पाठ और संबंधित जानकारी शामिल है.

#### प्रश्न: निकाले गए पाठ खंडों से मैं क्या जानकारी प्राप्त कर सकता हूँ?

उत्तर: आप निकाले गए टेक्स्ट सेगमेंट से विभिन्न विवरण प्राप्त कर सकते हैं, जिसमें टेक्स्ट सामग्री, स्थिति (X और Y निर्देशांक), फ़ॉन्ट जानकारी (नाम, आकार, रंग, आदि) और बहुत कुछ शामिल है। ट्यूटोरियल का नमूना कोड दर्शाता है कि प्रत्येक टेक्स्ट सेगमेंट के लिए इन विवरणों तक कैसे पहुँचें और उन्हें कैसे प्रिंट करें।

#### प्रश्न: क्या मैं निकाले गए पाठ खंडों पर कस्टम क्रियाएं कर सकता हूं?

उत्तर: निश्चित रूप से। एक बार जब आपके पास निकाले गए टेक्स्ट सेगमेंट आ जाते हैं, तो आप प्रत्येक सेगमेंट पर अतिरिक्त क्रियाएँ करने के लिए लूप के भीतर कोड को कस्टमाइज़ कर सकते हैं। इसमें निकाले गए टेक्स्ट को सहेजना, टेक्स्ट पैटर्न का विश्लेषण करना या फ़ॉर्मेटिंग परिवर्तन लागू करना शामिल हो सकता है।