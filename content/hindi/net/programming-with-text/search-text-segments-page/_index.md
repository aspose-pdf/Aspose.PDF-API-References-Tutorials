---
title: पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें
linktitle: पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि PDF फ़ाइल में पृष्ठ पर पाठ खंडों को कैसे खोजा जाए और .NET के लिए Aspose.PDF का उपयोग करके उनके गुणों को कैसे प्राप्त किया जाए।
type: docs
weight: 470
url: /hi/net/programming-with-text/search-text-segments-page/
---
यह ट्यूटोरियल बताता है कि PDF फ़ाइल के किसी पृष्ठ पर विशिष्ट टेक्स्ट खंडों को खोजने और उनके गुणों को पुनः प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

## चरण 3: दस्तावेज़ निर्देशिका का पथ सेट करें

 का उपयोग करके अपने दस्तावेज़ निर्देशिका का पथ सेट करें`dataDir` चर:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 4: पीडीएफ दस्तावेज़ लोड करें

 पीडीएफ दस्तावेज़ को लोड करें`Document` कक्षा:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 प्रतिस्थापित करें`"SearchTextSegmentsPage.pdf"` अपनी पीडीएफ फाइल के वास्तविक नाम के साथ।

## चरण 5: एक टेक्स्टफ़्रेगमेंटअब्ज़ॉर्बर बनाएँ

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

## चरण 8: पाठ खंडों के माध्यम से लूप करें

प्राप्त पाठ खंडों को लूप करें और उनके गुणों तक पहुंचें:

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

यदि आवश्यक हो तो प्रत्येक पाठ खंड पर आगे की क्रियाएं करने के लिए लूप के भीतर कोड को संशोधित करें।

### .NET के लिए Aspose.PDF का उपयोग करके खोज टेक्स्ट सेगमेंट पृष्ठ के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएँ
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप
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

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के पृष्ठ पर विशिष्ट टेक्स्ट सेगमेंट की खोज कैसे करें। इस ट्यूटोरियल में दस्तावेज़ लोड करने से लेकर निकाले गए टेक्स्ट सेगमेंट तक पहुँचने तक चरण-दर-चरण मार्गदर्शन प्रदान किया गया है। अब आप PDF फ़ाइलों में उन्नत टेक्स्ट सेगमेंट खोज करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें" ट्यूटोरियल एक व्यापक गाइड प्रदान करता है कि पीडीएफ दस्तावेज़ के किसी विशेष पृष्ठ पर विशिष्ट टेक्स्ट सेगमेंट की खोज करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। इसमें प्रोजेक्ट सेट अप करने, पीडीएफ दस्तावेज़ लोड करने, टेक्स्ट सेगमेंट की खोज करने और C# कोड का उपयोग करके उनके गुणों को पुनः प्राप्त करने की प्रक्रिया शामिल है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में विशिष्ट पाठ खंडों की खोज करने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल पीडीएफ दस्तावेज़ के किसी विशेष पृष्ठ पर विशिष्ट टेक्स्ट खंडों को खोजने और निकालने की प्रक्रिया को प्रदर्शित करता है। दिए गए चरणों और कोड नमूनों का पालन करके, उपयोगकर्ता प्रभावी रूप से वांछित टेक्स्ट खंडों की खोज कर सकते हैं और उनके गुणों के बारे में जानकारी प्राप्त कर सकते हैं।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए क्या पूर्वापेक्षाएँ आवश्यक हैं?

उत्तर: ट्यूटोरियल शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपके पास .NET लाइब्रेरी के लिए Aspose.PDF स्थापित होना चाहिए। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या NuGet का उपयोग करके अपने प्रोजेक्ट में इंस्टॉल कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उत्तर: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। यह आपको PDF दस्तावेज़ों को खोजने और उनके साथ काम करने के लिए लाइब्रेरी की सुविधाओं का उपयोग करने में सक्षम करेगा।

#### प्रश्न: क्या मैं इस ट्यूटोरियल का उपयोग पीडीएफ के किसी भी पृष्ठ पर विशिष्ट पाठ खंडों की खोज के लिए कर सकता हूं?

उत्तर: हाँ, यह ट्यूटोरियल PDF दस्तावेज़ के चयनित पृष्ठ पर विशिष्ट टेक्स्ट खंडों की खोज करने के तरीके के बारे में निर्देश प्रदान करता है। यह उपयोगकर्ताओं को प्रोजेक्ट सेट अप करने, PDF लोड करने और वांछित टेक्स्ट खंडों के गुणों का पता लगाने और उन्हें पुनः प्राप्त करने के लिए Aspose.PDF लाइब्रेरी का उपयोग करने के बारे में मार्गदर्शन करता है।

#### प्रश्न: मैं इस ट्यूटोरियल में जिस पाठ की खोज करना चाहता हूँ उसे कैसे निर्दिष्ट करूँ?

 उत्तर: आप जिस पाठ को खोजना चाहते हैं उसे निर्दिष्ट करने के लिए एक बनाएँ`TextFragmentAbsorber` ऑब्जेक्ट और इसका उपयोग करके खोज पैरामीटर सेट करें`Text` प्रॉपर्टी. डिफ़ॉल्ट को बदलें`"text"` ट्यूटोरियल के कोड में अपने इच्छित खोज वाक्यांश के साथ खोजें।

#### प्रश्न: मैं निकाले गए पाठ खंडों के गुण कैसे प्राप्त करूं?

स्वीकार करने के बाद`TextFragmentAbsorber` पीडीएफ के किसी विशिष्ट पृष्ठ के लिए, आप निकाले गए पाठ खंडों को पुनः प्राप्त कर सकते हैं`TextFragments` अवशोषक ऑब्जेक्ट की संपत्ति। यह पाठ अंशों के संग्रह तक पहुँच प्रदान करता है, जिनमें से प्रत्येक में कई पाठ खंड होते हैं।

#### प्रश्न: क्या मैं प्रत्येक पाठ खंड पर अतिरिक्त क्रियाएं करने के लिए कोड को अनुकूलित कर सकता हूं?

उत्तर: बिल्कुल। ट्यूटोरियल का नमूना कोड पुनर्प्राप्त किए गए टेक्स्ट सेगमेंट के माध्यम से पुनरावृति करने के लिए एक लूप प्रदान करता है। आप अपनी परियोजना आवश्यकताओं के आधार पर प्रत्येक टेक्स्ट सेगमेंट पर अतिरिक्त क्रियाएँ करने के लिए इस लूप के भीतर कोड को अनुकूलित कर सकते हैं।

#### प्रश्न: पाठ खंडों को निकालने के बाद मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेज सकता हूं?

उत्तर: यह ट्यूटोरियल मुख्य रूप से टेक्स्ट सेगमेंट की खोज करने और उनके गुणों को पुनः प्राप्त करने पर केंद्रित है। यदि आप PDF में संशोधन करने का इरादा रखते हैं, तो आप अपनी विशिष्ट आवश्यकताओं के आधार पर दस्तावेज़ में हेरफेर करने और उसे सहेजने का तरीका जानने के लिए अन्य Aspose.PDF दस्तावेज़ों का संदर्भ ले सकते हैं।