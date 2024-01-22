---
title: पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें
linktitle: पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: पीडीएफ फ़ाइल में किसी पृष्ठ पर टेक्स्ट सेगमेंट की खोज करना और .NET के लिए Aspose.PDF का उपयोग करके उनके गुणों को पुनः प्राप्त करना सीखें।
type: docs
weight: 470
url: /hi/net/programming-with-text/search-text-segments-page/
---
यह ट्यूटोरियल बताता है कि पीडीएफ फ़ाइल के एक पृष्ठ पर विशिष्ट पाठ खंडों को खोजने और उनके गुणों को पुनः प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

## चरण 3: दस्तावेज़ निर्देशिका के लिए पथ सेट करें

 का उपयोग करके अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करें`dataDir` चर:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 4: पीडीएफ दस्तावेज़ लोड करें

 का उपयोग करके पीडीएफ दस्तावेज़ लोड करें`Document` कक्षा:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 प्रतिस्थापित करें`"SearchTextSegmentsPage.pdf"` आपकी पीडीएफ फाइल के वास्तविक नाम के साथ।

## चरण 5: एक टेक्स्टफ्रैगमेंटएब्जॉर्बर बनाएं

 एक बनाने के`TextFragmentAbsorber` इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए ऑब्जेक्ट:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 प्रतिस्थापित करें`"text"` अपने इच्छित खोज वाक्यांश के साथ.

## चरण 6: किसी विशिष्ट पृष्ठ के लिए अवशोषक स्वीकार करें

दस्तावेज़ के वांछित पृष्ठ के लिए अवशोषक स्वीकार करें:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 प्रतिस्थापित करें`2` वांछित पृष्ठ संख्या (1-आधारित सूचकांक) के साथ।

## चरण 7: निकाले गए पाठ खंडों को पुनः प्राप्त करें

 का उपयोग करके निकाले गए पाठ खंड प्राप्त करें`TextFragments` की संपत्ति`TextFragmentAbsorber` वस्तु:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## चरण 8: टेक्स्ट खंडों के माध्यम से लूप करें

पुनर्प्राप्त पाठ खंडों के माध्यम से लूप करें और उनके गुणों तक पहुंचें:

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

यदि आवश्यक हो तो प्रत्येक टेक्स्ट सेगमेंट पर आगे की कार्रवाई करने के लिए लूप के भीतर कोड को संशोधित करें।

### .NET के लिए Aspose.PDF का उपयोग करके खोज टेक्स्ट सेगमेंट पेज के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए टेक्स्टएब्जॉर्बर ऑब्जेक्ट बनाएं
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप करें
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के एक पृष्ठ पर विशिष्ट पाठ खंडों को खोजना सफलतापूर्वक सीख लिया है। यह ट्यूटोरियल दस्तावेज़ को लोड करने से लेकर निकाले गए टेक्स्ट सेगमेंट तक पहुंचने तक चरण-दर-चरण मार्गदर्शिका प्रदान करता है। अब आप पीडीएफ फाइलों में उन्नत टेक्स्ट सेगमेंट खोज करने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें" ट्यूटोरियल पीडीएफ दस्तावेज़ के किसी विशेष पृष्ठ पर विशिष्ट टेक्स्ट सेगमेंट की खोज के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने के तरीके पर एक व्यापक मार्गदर्शिका प्रदान करता है। इसमें एक प्रोजेक्ट स्थापित करने, एक पीडीएफ दस्तावेज़ लोड करने, टेक्स्ट सेगमेंट की खोज करने और सी# कोड का उपयोग करके उनकी संपत्तियों को पुनर्प्राप्त करने की प्रक्रिया शामिल है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में विशिष्ट पाठ खंडों को खोजने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल पीडीएफ दस्तावेज़ के किसी विशेष पृष्ठ पर विशिष्ट पाठ खंडों को ढूंढने और निकालने की प्रक्रिया को प्रदर्शित करता है। दिए गए चरणों और कोड नमूनों का पालन करके, उपयोगकर्ता प्रभावी ढंग से वांछित पाठ खंडों की खोज कर सकते हैं और उनकी संपत्तियों के बारे में जानकारी प्राप्त कर सकते हैं।

#### प्रश्न: इस ट्यूटोरियल का पालन करने के लिए किन पूर्वावश्यकताओं की आवश्यकता है?

उत्तर: ट्यूटोरियल शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपको .NET लाइब्रेरी के लिए Aspose.PDF स्थापित करना होगा। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या NuGet का उपयोग करके इसे अपने प्रोजेक्ट में इंस्टॉल कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उ: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाएं और .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें। यह आपको पीडीएफ दस्तावेज़ों को खोजने और उनके साथ काम करने के लिए लाइब्रेरी की सुविधाओं का उपयोग करने में सक्षम करेगा।

#### प्रश्न: क्या मैं पीडीएफ के किसी भी पृष्ठ पर विशिष्ट पाठ खंडों की खोज के लिए इस ट्यूटोरियल का उपयोग कर सकता हूं?

उ: हां, यह ट्यूटोरियल पीडीएफ दस्तावेज़ के चयनित पृष्ठ पर विशिष्ट पाठ खंडों की खोज करने के तरीके के बारे में निर्देश प्रदान करता है। यह उपयोगकर्ताओं को प्रोजेक्ट स्थापित करने, पीडीएफ लोड करने और वांछित टेक्स्ट सेगमेंट के गुणों का पता लगाने और पुनर्प्राप्त करने के लिए Aspose.PDF लाइब्रेरी का उपयोग करने में मार्गदर्शन करता है।

#### प्रश्न: मैं इस ट्यूटोरियल में जिस टेक्स्ट को खोजना चाहता हूं उसे कैसे निर्दिष्ट करूं?

 उ: उस पाठ को निर्दिष्ट करने के लिए जिसे आप खोजना चाहते हैं, एक बनाएं`TextFragmentAbsorber` ऑब्जेक्ट बनाएं और इसका उपयोग करके उसका खोज पैरामीटर सेट करें`Text` संपत्ति। डिफ़ॉल्ट बदलें`"text"` अपने इच्छित खोज वाक्यांश के साथ ट्यूटोरियल के कोड में।

#### प्रश्न: मैं निकाले गए पाठ खंडों के गुणों को कैसे पुनः प्राप्त करूं?

स्वीकार करने के बाद`TextFragmentAbsorber` पीडीएफ के एक विशिष्ट पृष्ठ के लिए, आप इसका उपयोग करके निकाले गए पाठ खंडों को पुनः प्राप्त कर सकते हैं`TextFragments` अवशोषक वस्तु की संपत्ति. यह पाठ खंडों के संग्रह तक पहुंच प्रदान करता है, जिनमें से प्रत्येक में एकाधिक पाठ खंड होते हैं।

#### प्रश्न: क्या मैं प्रत्येक पाठ खंड पर अतिरिक्त क्रियाएं करने के लिए कोड को अनुकूलित कर सकता हूं?

उत्तर: बिल्कुल. ट्यूटोरियल का नमूना कोड पुनर्प्राप्त पाठ खंडों के माध्यम से पुनरावृत्त करने के लिए एक लूप प्रदान करता है। आप अपनी प्रोजेक्ट आवश्यकताओं के आधार पर प्रत्येक टेक्स्ट सेगमेंट पर अतिरिक्त क्रियाएं करने के लिए इस लूप के भीतर कोड को कस्टमाइज़ कर सकते हैं।

#### प्रश्न: टेक्स्ट खंड निकालने के बाद मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूं?

उत्तर: यह ट्यूटोरियल मुख्य रूप से टेक्स्ट सेगमेंट की खोज करने और उनके गुणों को पुनः प्राप्त करने पर केंद्रित है। यदि आप पीडीएफ में संशोधन करने का इरादा रखते हैं, तो आप अपनी विशिष्ट आवश्यकताओं के आधार पर दस्तावेज़ में हेरफेर करने और सहेजने का तरीका जानने के लिए अन्य Aspose.PDF दस्तावेज़ का संदर्भ ले सकते हैं।