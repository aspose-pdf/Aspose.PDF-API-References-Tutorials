---
title: खोजें और सभी पाठ प्राप्त करें
linktitle: खोजें और सभी पाठ प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके किसी PDF दस्तावेज़ के सभी पृष्ठों से पाठ खोजना और प्राप्त करना सीखें।
type: docs
weight: 420
url: /hi/net/programming-with-text/search-and-get-text-all/
---
यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के सभी पृष्ठों से टेक्स्ट कैसे खोजा और प्राप्त किया जाए। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 4: पाठ खोजें और निकालें

 एक बनाने के`TextFragmentAbsorber` इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए ऑब्जेक्ट:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 प्रतिस्थापित करें`"text"` उस वास्तविक पाठ के साथ जिसे आप खोजना चाहते हैं.

## चरण 5: सभी पृष्ठों पर खोजें

दस्तावेज़ के सभी पृष्ठों के लिए अवशोषक स्वीकार करें:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## चरण 6: निकाले गए पाठ अंश प्राप्त करें

 का उपयोग करके निकाले गए पाठ अंश प्राप्त करें`TextFragments` की संपत्ति`TextFragmentAbsorber` वस्तु:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## चरण 7: पाठ अंशों के माध्यम से लूप करें

getd पाठ अंशों के माध्यम से लूप करें और उनके गुणों तक पहुँचें:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

आप प्रत्येक पाठ खंड पर आगे की क्रियाएं करने के लिए लूप के भीतर कोड को संशोधित कर सकते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके सभी टेक्स्ट खोजने और प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएँ
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages.Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के सभी पृष्ठों से टेक्स्ट कैसे खोजें और प्राप्त करें। इस ट्यूटोरियल में दस्तावेज़ लोड करने से लेकर निकाले गए टेक्स्ट अंशों तक पहुँचने तक चरण-दर-चरण मार्गदर्शन प्रदान किया गया है। अब आप PDF फ़ाइलों में टेक्स्ट सामग्री का विश्लेषण और प्रक्रिया करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "सभी टेक्स्ट खोजें और प्राप्त करें" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "खोजें और सभी टेक्स्ट प्राप्त करें" ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें ताकि PDF दस्तावेज़ के सभी पृष्ठों से टेक्स्ट खोजा और निकाला जा सके। ट्यूटोरियल टेक्स्ट खोज और पुनर्प्राप्ति करने के लिए नमूना C# कोड के साथ चरण-दर-चरण निर्देश प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेजों से टेक्स्ट निकालने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल आपको PDF दस्तावेज़ के सभी पृष्ठों से टेक्स्ट निकालने की प्रक्रिया के बारे में बताता है। यह विशिष्ट टेक्स्ट वाक्यांशों का पता लगाने और संबंधित जानकारी, जैसे कि स्थिति, फ़ॉन्ट गुण और रंग, को पुनः प्राप्त करने के लिए Aspose.PDF लाइब्रेरी का उपयोग करता है।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए पूर्वापेक्षाएँ क्या हैं?

उत्तर: इस ट्यूटोरियल को शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपके पास .NET लाइब्रेरी के लिए Aspose.PDF स्थापित होना चाहिए। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में एकीकृत करने के लिए NuGet का उपयोग कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उत्तर: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। यह आपको अपनी परियोजना में लाइब्रेरी की कार्यक्षमता तक पहुँचने की अनुमति देगा।

#### प्रश्न: मैं किसी PDF दस्तावेज़ में विशिष्ट पाठ कैसे खोज सकता हूँ?

 उत्तर: आप इसका उपयोग कर सकते हैं`TextFragmentAbsorber`पीडीएफ दस्तावेज़ के भीतर एक विशिष्ट खोज वाक्यांश के उदाहरण खोजने के लिए क्लास। इस क्लास का एक उदाहरण बनाकर और लक्ष्य पाठ निर्दिष्ट करके, आप उस पाठ की सभी घटनाओं को कैप्चर कर सकते हैं।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ के सभी पृष्ठों पर पाठ खोज सकता हूँ?

 उत्तर: हां, ट्यूटोरियल यह दर्शाता है कि पीडीएफ दस्तावेज़ के सभी पृष्ठों पर टेक्स्ट की खोज कैसे करें।`pdfDocument.Pages.Accept(textFragmentAbsorber)` विधि का उपयोग सभी पृष्ठों के लिए अवशोषक को स्वीकार करने के लिए किया जाता है, जिससे आप प्रत्येक पृष्ठ पर वांछित पाठ खोज सकते हैं।

#### प्रश्न: मैं निकाले गए पाठ अंशों तक कैसे पहुंच सकता हूं?

 उत्तर: पाठ की खोज करने के बाद, आप निकाले गए पाठ अंशों तक पहुंच सकते हैं`TextFragments` की संपत्ति`TextFragmentAbsorber` ऑब्जेक्ट. यह प्रॉपर्टी संग्रह तक पहुंच प्रदान करती है`TextFragment` वे ऑब्जेक्ट जिनमें निकाला गया पाठ और संबंधित जानकारी शामिल है.

#### प्रश्न: निकाले गए पाठ अंशों से मैं क्या जानकारी प्राप्त कर सकता हूँ?

उत्तर: आप निकाले गए टेक्स्ट अंशों से विभिन्न विवरण प्राप्त कर सकते हैं, जैसे कि वास्तविक टेक्स्ट सामग्री, स्थिति (X और Y निर्देशांक), फ़ॉन्ट जानकारी (नाम, आकार, रंग, आदि), और बहुत कुछ। ट्यूटोरियल का नमूना कोड दर्शाता है कि इन विवरणों तक कैसे पहुँचें और उन्हें कैसे प्रिंट करें।

#### प्रश्न: क्या मैं निकाले गए पाठ अंशों पर आगे की कार्रवाई कर सकता हूँ?

उत्तर: बिल्कुल। एक बार जब आपके पास निकाले गए टेक्स्ट फ़्रैगमेंट आ जाते हैं, तो आप लूप के भीतर कोड को संशोधित कर सकते हैं ताकि प्रत्येक फ़्रैगमेंट पर कस्टम क्रियाएँ की जा सकें। इसमें निकाले गए टेक्स्ट को सहेजना, टेक्स्ट पैटर्न का विश्लेषण करना या फ़ॉर्मेटिंग परिवर्तन लागू करना शामिल हो सकता है।