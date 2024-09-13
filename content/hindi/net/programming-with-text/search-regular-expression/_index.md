---
title: पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें
linktitle: पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में नियमित अभिव्यक्तियों का उपयोग करके पाठ को खोजना और पुनर्प्राप्त करना सीखें।
type: docs
weight: 440
url: /hi/net/programming-with-text/search-regular-expression/
---
यह ट्यूटोरियल बताता है कि PDF फ़ाइल में रेगुलर एक्सप्रेशन से मेल खाने वाले टेक्स्ट को खोजने और प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड प्रक्रिया को चरण दर चरण प्रदर्शित करता है।

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 4: नियमित अभिव्यक्ति के साथ खोजें

 एक बनाने के`TextFragmentAbsorber` ऑब्जेक्ट और पैटर्न से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए नियमित अभिव्यक्ति पैटर्न सेट करें:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 की तरह
```

 प्रतिस्थापित करें`"\\d{4}-\\d{4}"` अपने इच्छित नियमित अभिव्यक्ति पैटर्न के साथ।

## चरण 5: पाठ खोज विकल्प सेट करें

 एक बनाने के`TextSearchOptions` ऑब्जेक्ट और इसे सेट करें`TextSearchOptions` की संपत्ति`TextFragmentAbsorber` नियमित अभिव्यक्ति उपयोग को सक्षम करने के लिए ऑब्जेक्ट:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## चरण 6: सभी पृष्ठों पर खोजें

दस्तावेज़ के सभी पृष्ठों के लिए अवशोषक स्वीकार करें:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## चरण 7: निकाले गए पाठ अंशों को पुनः प्राप्त करें

 का उपयोग करके निकाले गए पाठ अंश प्राप्त करें`TextFragments` की संपत्ति`TextFragmentAbsorber` वस्तु:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## चरण 8: पाठ अंशों के माध्यम से लूप करें

प्राप्त पाठ अंशों को लूप करें और उनके गुणों तक पहुंचें:

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

### .NET के लिए Aspose.PDF का उपयोग करके सर्च रेगुलर एक्सप्रेशन के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//नियमित अभिव्यक्ति से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएं
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 की तरह
// नियमित अभिव्यक्ति उपयोग निर्दिष्ट करने के लिए पाठ खोज विकल्प सेट करें
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में नियमित अभिव्यक्ति से मेल खाने वाले टेक्स्ट को कैसे खोजा और प्राप्त किया जाए। इस ट्यूटोरियल में दस्तावेज़ को लोड करने से लेकर निकाले गए टेक्स्ट अंशों तक पहुँचने तक चरण-दर-चरण मार्गदर्शन प्रदान किया गया है। अब आप PDF फ़ाइलों में उन्नत टेक्स्ट खोज करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें" ट्यूटोरियल का उद्देश्य यह दिखाना है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें ताकि पीडीएफ फाइल में निर्दिष्ट रेगुलर एक्सप्रेशन पैटर्न से मेल खाने वाले टेक्स्ट को खोजा और निकाला जा सके। ट्यूटोरियल प्रक्रिया को प्रदर्शित करने के लिए व्यापक मार्गदर्शन और नमूना C# कोड प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में नियमित अभिव्यक्तियों का उपयोग करके पाठ खोजने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल एक नियमित अभिव्यक्ति पैटर्न के आधार पर PDF दस्तावेज़ में टेक्स्ट खोज करने के लिए Aspose.PDF लाइब्रेरी का उपयोग करने के लिए चरण-दर-चरण दृष्टिकोण प्रदान करता है। यह विस्तार से बताता है कि प्रोजेक्ट को कैसे सेट अप करें, PDF दस्तावेज़ को कैसे लोड करें, एक नियमित अभिव्यक्ति पैटर्न को कैसे परिभाषित करें, और मिलान करने वाले टेक्स्ट अंशों को कैसे प्राप्त करें।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए पूर्वापेक्षाएँ क्या हैं?

उत्तर: इस ट्यूटोरियल को शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपके पास .NET लाइब्रेरी के लिए Aspose.PDF स्थापित होना चाहिए। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में एकीकृत करने के लिए NuGet का उपयोग कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उत्तर: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। इससे आप अपनी परियोजना के भीतर लाइब्रेरी की क्षमताओं का लाभ उठा सकेंगे।

#### प्रश्न: क्या मैं PDF दस्तावेज़ में पाठ खोजने के लिए नियमित अभिव्यक्ति का उपयोग कर सकता हूँ?

 उत्तर: हाँ, यह ट्यूटोरियल दर्शाता है कि PDF दस्तावेज़ से टेक्स्ट खोजने और निकालने के लिए रेगुलर एक्सप्रेशन का उपयोग कैसे करें। इसमें उपयोग करना शामिल है`TextFragmentAbsorber` क्लास में नियमित अभिव्यक्ति पैटर्न निर्दिष्ट करना और दिए गए पैटर्न से मेल खाने वाले वाक्यांशों को ढूंढना।

#### प्रश्न: मैं पाठ खोज के लिए नियमित अभिव्यक्ति पैटर्न कैसे परिभाषित करूं?

 उत्तर: पाठ खोज के लिए एक नियमित अभिव्यक्ति पैटर्न परिभाषित करने के लिए, एक बनाएँ`TextFragmentAbsorber` ऑब्जेक्ट और इसका पैटर्न सेट करें`Text` पैरामीटर. डिफ़ॉल्ट पैटर्न बदलें`"\\d{4}-\\d{4}"` ट्यूटोरियल के कोड में अपने इच्छित नियमित अभिव्यक्ति पैटर्न के साथ।

#### प्रश्न: मैं पाठ खोज के लिए नियमित अभिव्यक्ति का उपयोग कैसे सक्षम कर सकता हूं?

 A: नियमित अभिव्यक्ति का उपयोग एक बनाकर सक्षम किया जाता है`TextSearchOptions` ऑब्जेक्ट और उसका मान सेट करना`true` . इस ऑब्जेक्ट को असाइन करें`TextSearchOptions` की संपत्ति`TextFragmentAbsorber` यह सुनिश्चित करता है कि नियमित अभिव्यक्ति पैटर्न पाठ खोज के दौरान लागू किया जाता है।

#### प्रश्न: क्या मैं नियमित अभिव्यक्ति पैटर्न से मेल खाने वाले पाठ अंश पुनः प्राप्त कर सकता हूँ?

 उत्तर: बिल्कुल। PDF दस्तावेज़ पर नियमित अभिव्यक्ति खोज लागू करने के बाद, आप निकाले गए पाठ अंशों को पुनः प्राप्त कर सकते हैं`TextFragments` की संपत्ति`TextFragmentAbsorber` ऑब्जेक्ट. इन पाठ अंशों में वे पाठ खंड होते हैं जो निर्दिष्ट नियमित अभिव्यक्ति पैटर्न से मेल खाते हैं.

#### प्रश्न: मैं पुनः प्राप्त पाठ अंशों से क्या प्राप्त कर सकता हूँ?

उत्तर: प्राप्त किए गए टेक्स्ट अंशों से, आप विभिन्न गुणों जैसे कि मिलान किए गए टेक्स्ट कंटेंट, स्थिति (X और Y निर्देशांक), फ़ॉन्ट जानकारी (नाम, आकार, रंग), और बहुत कुछ तक पहुँच सकते हैं। ट्यूटोरियल के लूप के भीतर नमूना कोड दर्शाता है कि इन गुणों तक कैसे पहुँचें और उन्हें कैसे प्रदर्शित करें।

#### प्रश्न: मैं निकाले गए पाठ अंशों पर क्रियाओं को कैसे अनुकूलित कर सकता हूं?

उत्तर: एक बार जब आपके पास निकाले गए टेक्स्ट फ़्रैगमेंट आ जाते हैं, तो आप लूप के भीतर कोड को कस्टमाइज़ कर सकते हैं ताकि प्रत्येक टेक्स्ट फ़्रैगमेंट पर अतिरिक्त क्रियाएँ की जा सकें। इसमें निकाले गए टेक्स्ट को सहेजना, पैटर्न का विश्लेषण करना या अपनी आवश्यकताओं के आधार पर फ़ॉर्मेटिंग परिवर्तन लागू करना शामिल हो सकता है।