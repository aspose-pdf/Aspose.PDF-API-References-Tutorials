---
title: पीडीएफ फाइल में टेक्स्ट पेज खोजें और प्राप्त करें
linktitle: पीडीएफ फाइल में टेक्स्ट पेज खोजें और प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में किसी विशिष्ट पृष्ठ से टेक्स्ट कैसे खोजना और प्राप्त करना सीखें।
type: docs
weight: 430
url: /hi/net/programming-with-text/search-and-get-text-page/
---
यह ट्यूटोरियल बताता है कि पीडीएफ फाइल में किसी विशिष्ट पेज से टेक्स्ट खोजने और प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

## आवश्यक शर्तें

ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में इंस्टॉल करने के लिए NuGet का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें

अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाकर शुरुआत करें और .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें

आवश्यक नामस्थान आयात करने के लिए अपनी C# फ़ाइल की शुरुआत में निम्नलिखित निर्देशों का उपयोग करके जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: पीडीएफ दस्तावेज़ लोड करें

 अपनी पीडीएफ दस्तावेज़ निर्देशिका के लिए पथ सेट करें और इसका उपयोग करके दस्तावेज़ को लोड करें`Document` कक्षा:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 4: किसी पृष्ठ से टेक्स्ट खोजें और निकालें

 एक बनाने के`TextFragmentAbsorber`किसी विशिष्ट पृष्ठ पर इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए ऑब्जेक्ट:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 प्रतिस्थापित करें`"Figure"` उस वास्तविक पाठ के साथ जिसे आप खोजना चाहते हैं।

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

## चरण 7: पाठ के अंशों और खंडों के माध्यम से लूप करें

प्राप्त पाठ अंशों और उनके खंडों के माध्यम से लूप करें, और उनके गुणों तक पहुंचें:

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

आप प्रत्येक टेक्स्ट सेगमेंट पर आगे की कार्रवाई करने के लिए लूप के भीतर कोड को संशोधित कर सकते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट पेज खोजें और प्राप्त करें के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए टेक्स्टएब्जॉर्बर ऑब्जेक्ट बनाएं
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages.Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप करें
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

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के एक विशिष्ट पृष्ठ से टेक्स्ट कैसे खोजना और प्राप्त करना सफलतापूर्वक सीख लिया है। यह ट्यूटोरियल दस्तावेज़ को लोड करने से लेकर निकाले गए टेक्स्ट सेगमेंट तक पहुंचने तक चरण-दर-चरण मार्गदर्शिका प्रदान करता है। अब आप शामिल कर सकते हैं

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "खोजें और टेक्स्ट पेज प्राप्त करें" ट्यूटोरियल का उद्देश्य क्या है?

उ: "खोजें और टेक्स्ट पेज प्राप्त करें" ट्यूटोरियल यह समझाने के लिए डिज़ाइन किया गया है कि पीडीएफ फाइल के भीतर एक विशिष्ट पेज से टेक्स्ट को खोजने और पुनर्प्राप्त करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। प्रक्रिया को प्रदर्शित करने के लिए ट्यूटोरियल विस्तृत निर्देश और नमूना C# कोड प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में किसी विशिष्ट पृष्ठ से टेक्स्ट निकालने में कैसे मदद करता है?

उ: यह ट्यूटोरियल आपको Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ के एक विशेष पृष्ठ से पाठ निकालने की प्रक्रिया में मार्गदर्शन करता है। यह आवश्यक चरणों की रूपरेखा तैयार करता है और चयनित पृष्ठ पर एक निर्दिष्ट पाठ वाक्यांश की खोज करने और संबंधित पाठ खंडों को पुनः प्राप्त करने के लिए C# कोड प्रदान करता है।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए आवश्यक शर्तें क्या हैं?

उत्तर: इस ट्यूटोरियल को शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपको .NET लाइब्रेरी के लिए Aspose.PDF स्थापित करना होगा। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में एकीकृत करने के लिए NuGet का उपयोग कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उ: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाएं और .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें। यह आपको अपने प्रोजेक्ट में लाइब्रेरी की क्षमताओं का उपयोग करने में सक्षम करेगा।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ के किसी विशिष्ट पृष्ठ पर पाठ खोज सकता हूँ?

उ: हां, यह ट्यूटोरियल दर्शाता है कि पीडीएफ दस्तावेज़ के विशिष्ट पृष्ठ पर टेक्स्ट की खोज कैसे करें। इसमें का उपयोग करना शामिल है`TextFragmentAbsorber` चुने गए पृष्ठ पर किसी विशेष पाठ वाक्यांश के उदाहरणों का पता लगाने के लिए कक्षा।

#### प्रश्न: मैं विशिष्ट पृष्ठ से निकाले गए पाठ खंडों तक कैसे पहुंच सकता हूं?

 उ: निर्दिष्ट पृष्ठ पर पाठ की खोज करने के बाद, आप इसका उपयोग करके निकाले गए पाठ खंडों तक पहुंच सकते हैं`TextSegments` की संपत्ति`TextFragment` वस्तु। यह संपत्ति संग्रह तक पहुंच प्रदान करती है`TextSegment` वे वस्तुएँ जिनमें निकाला गया पाठ और संबंधित जानकारी होती है।

#### प्रश्न: मैं निकाले गए पाठ खंडों से कौन सी जानकारी प्राप्त कर सकता हूं?

उ: आप निकाले गए पाठ खंडों से विभिन्न विवरण प्राप्त कर सकते हैं, जिसमें पाठ सामग्री, स्थिति (एक्स और वाई निर्देशांक), फ़ॉन्ट जानकारी (नाम, आकार, रंग, आदि), और बहुत कुछ शामिल है। ट्यूटोरियल का नमूना कोड दर्शाता है कि प्रत्येक टेक्स्ट सेगमेंट के लिए इन विवरणों को कैसे एक्सेस और प्रिंट किया जाए।

#### प्रश्न: क्या मैं निकाले गए टेक्स्ट सेगमेंट पर कस्टम क्रियाएं कर सकता हूं?

ए: निश्चित रूप से. एक बार जब आपके पास निकाले गए टेक्स्ट सेगमेंट हों, तो आप प्रत्येक सेगमेंट पर अतिरिक्त क्रियाएं करने के लिए लूप के भीतर कोड को कस्टमाइज़ कर सकते हैं। इसमें निकाले गए टेक्स्ट को सहेजना, टेक्स्ट पैटर्न का विश्लेषण करना या फ़ॉर्मेटिंग परिवर्तन लागू करना शामिल हो सकता है।