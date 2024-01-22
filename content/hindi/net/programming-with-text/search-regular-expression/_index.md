---
title: पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें
linktitle: पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में रेगुलर एक्सप्रेशन का उपयोग करके टेक्स्ट को खोजना और पुनः प्राप्त करना सीखें।
type: docs
weight: 440
url: /hi/net/programming-with-text/search-regular-expression/
---
यह ट्यूटोरियल बताता है कि पीडीएफ फाइल में रेगुलर एक्सप्रेशन से मेल खाने वाले टेक्स्ट को खोजने और पुनः प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 4: रेगुलर एक्सप्रेशन के साथ खोजें

 एक बनाने के`TextFragmentAbsorber` ऑब्जेक्ट करें और पैटर्न से मेल खाने वाले सभी वाक्यांशों को ढूंढने के लिए नियमित अभिव्यक्ति पैटर्न सेट करें:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // जैसे 1999-2000
```

 प्रतिस्थापित करें`"\\d{4}-\\d{4}"` अपने वांछित नियमित अभिव्यक्ति पैटर्न के साथ।

## चरण 5: पाठ खोज विकल्प सेट करें

 एक बनाने के`TextSearchOptions` ऑब्जेक्ट करें और इसे पर सेट करें`TextSearchOptions` की संपत्ति`TextFragmentAbsorber` नियमित अभिव्यक्ति उपयोग को सक्षम करने के लिए ऑब्जेक्ट:

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

## चरण 8: पाठ के टुकड़ों को लूप करें

पुनर्प्राप्त पाठ अंशों के माध्यम से लूप करें और उनके गुणों तक पहुंचें:

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

आप प्रत्येक पाठ खंड पर आगे की कार्रवाई करने के लिए लूप के भीतर कोड को संशोधित कर सकते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके नियमित अभिव्यक्ति खोजने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// रेगुलर एक्सप्रेशन से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए टेक्स्टएब्जॉर्बर ऑब्जेक्ट बनाएं
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // जैसे 1999-2000
// नियमित अभिव्यक्ति उपयोग निर्दिष्ट करने के लिए पाठ खोज विकल्प सेट करें
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages.Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप करें
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

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में रेगुलर एक्सप्रेशन से मेल खाने वाले टेक्स्ट को खोजना और पुनः प्राप्त करना सफलतापूर्वक सीख लिया है। इस ट्यूटोरियल ने दस्तावेज़ को लोड करने से लेकर निकाले गए पाठ अंशों तक पहुँचने तक चरण-दर-चरण मार्गदर्शिका प्रदान की। अब आप पीडीएफ फाइलों में उन्नत टेक्स्ट खोज करने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में रेगुलर एक्सप्रेशन खोजें" ट्यूटोरियल का उद्देश्य यह दिखाना है कि पीडीएफ फाइल के भीतर एक निर्दिष्ट रेगुलर एक्सप्रेशन पैटर्न से मेल खाने वाले टेक्स्ट को खोजने और निकालने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल प्रक्रिया को प्रदर्शित करने के लिए व्यापक मार्गदर्शन और नमूना C# कोड प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में रेगुलर एक्सप्रेशन का उपयोग करके टेक्स्ट खोजने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल नियमित अभिव्यक्ति पैटर्न के आधार पर पीडीएफ दस्तावेज़ में पाठ खोज करने के लिए Aspose.PDF लाइब्रेरी का उपयोग करने के लिए चरण-दर-चरण दृष्टिकोण प्रदान करता है। इसमें बताया गया है कि प्रोजेक्ट कैसे सेट करें, पीडीएफ दस्तावेज़ को कैसे लोड करें, एक नियमित अभिव्यक्ति पैटर्न को परिभाषित करें और मिलान वाले पाठ अंशों को पुनः प्राप्त करें।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए आवश्यक शर्तें क्या हैं?

उत्तर: इस ट्यूटोरियल को शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपको .NET लाइब्रेरी के लिए Aspose.PDF स्थापित करना होगा। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में एकीकृत करने के लिए NuGet का उपयोग कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उ: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाएं और .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें। यह आपको अपने प्रोजेक्ट के भीतर लाइब्रेरी की क्षमताओं का लाभ उठाने की अनुमति देगा।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में टेक्स्ट खोजने के लिए रेगुलर एक्सप्रेशन का उपयोग कर सकता हूं?

 उ: हां, यह ट्यूटोरियल दर्शाता है कि पीडीएफ दस्तावेज़ से टेक्स्ट खोजने और निकालने के लिए नियमित अभिव्यक्ति का उपयोग कैसे करें। इसमें का उपयोग करना शामिल है`TextFragmentAbsorber` कक्षा और दिए गए पैटर्न से मेल खाने वाले वाक्यांशों को खोजने के लिए एक नियमित अभिव्यक्ति पैटर्न निर्दिष्ट करना।

#### प्रश्न: मैं पाठ खोज के लिए नियमित अभिव्यक्ति पैटर्न को कैसे परिभाषित करूं?

 ए: टेक्स्ट खोज के लिए नियमित अभिव्यक्ति पैटर्न को परिभाषित करने के लिए, एक बनाएं`TextFragmentAbsorber` ऑब्जेक्ट बनाएं और उसका पैटर्न सेट करें`Text` पैरामीटर. डिफ़ॉल्ट पैटर्न बदलें`"\\d{4}-\\d{4}"` अपने वांछित नियमित अभिव्यक्ति पैटर्न के साथ ट्यूटोरियल के कोड में।

#### प्रश्न: मैं टेक्स्ट खोज के लिए रेगुलर एक्सप्रेशन उपयोग कैसे सक्षम कर सकता हूं?

 ए: रेगुलर एक्सप्रेशन का उपयोग एक बनाकर सक्षम किया गया है`TextSearchOptions` ऑब्जेक्ट और उसका मान सेट करना`true` . इस ऑब्जेक्ट को असाइन करें`TextSearchOptions` की संपत्ति`TextFragmentAbsorber` उदाहरण। यह सुनिश्चित करता है कि पाठ खोज के दौरान नियमित अभिव्यक्ति पैटर्न लागू किया जाता है।

#### प्रश्न: क्या मैं नियमित अभिव्यक्ति पैटर्न से मेल खाने वाले पाठ अंशों को पुनः प्राप्त कर सकता हूँ?

 उत्तर: बिल्कुल. पीडीएफ दस्तावेज़ पर रेगुलर एक्सप्रेशन खोज लागू करने के बाद, आप इसका उपयोग करके निकाले गए पाठ अंशों को पुनः प्राप्त कर सकते हैं`TextFragments` की संपत्ति`TextFragmentAbsorber` वस्तु। इन पाठ खंडों में वे पाठ खंड शामिल हैं जो निर्दिष्ट नियमित अभिव्यक्ति पैटर्न से मेल खाते हैं।

#### प्रश्न: मैं पुनर्प्राप्त पाठ अंशों से क्या एक्सेस कर सकता हूं?

उ: पुनर्प्राप्त पाठ अंशों से, आप विभिन्न गुणों जैसे कि मिलान की गई पाठ सामग्री, स्थिति (एक्स और वाई निर्देशांक), फ़ॉन्ट जानकारी (नाम, आकार, रंग), और बहुत कुछ तक पहुंच सकते हैं। ट्यूटोरियल के लूप के भीतर नमूना कोड दर्शाता है कि इन गुणों तक कैसे पहुंचें और प्रदर्शित करें।

#### प्रश्न: मैं निकाले गए पाठ अंशों पर क्रियाओं को कैसे अनुकूलित कर सकता हूं?

उ: एक बार जब आपके पास निकाले गए टेक्स्ट टुकड़े हों, तो आप प्रत्येक टेक्स्ट टुकड़े पर अतिरिक्त क्रियाएं करने के लिए लूप के भीतर कोड को कस्टमाइज़ कर सकते हैं। इसमें निकाले गए पाठ को सहेजना, पैटर्न का विश्लेषण करना, या आपकी आवश्यकताओं के आधार पर स्वरूपण परिवर्तन लागू करना शामिल हो सकता है।