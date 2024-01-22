---
title: टेक्स्ट खोजें और आयत बनाएं
linktitle: टेक्स्ट खोजें और आयत बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि पीडीएफ में टेक्स्ट कैसे खोजें, पाए गए टेक्स्ट के चारों ओर आयत कैसे बनाएं, और .NET के लिए Aspose.PDF का उपयोग करके संशोधित दस्तावेज़ को सहेजें।
type: docs
weight: 460
url: /hi/net/programming-with-text/search-text-and-draw-rectangle/
---
यह ट्यूटोरियल बताता है कि पीडीएफ दस्तावेज़ में विशिष्ट पाठ की खोज करने, पाए गए पाठ के चारों ओर एक आयत बनाने और संशोधित दस्तावेज़ को सहेजने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 प्रतिस्थापित करें`"SearchAndGetTextFromAll.pdf"` आपकी पीडीएफ फाइल के वास्तविक नाम के साथ।

## चरण 5: एक टेक्स्टफ्रैगमेंटएब्जॉर्बर बनाएं

 एक बनाने के`TextFragmentAbsorber` इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए ऑब्जेक्ट:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 प्रतिस्थापित करें`@"[\S]+"` अपने वांछित नियमित अभिव्यक्ति पैटर्न के साथ।

## चरण 6: रेगुलर एक्सप्रेशन खोज सक्षम करें

 सेट करके रेगुलर एक्सप्रेशन खोज सक्षम करें`TextSearchOptions` अवशोषक की संपत्ति:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## चरण 7: सभी पृष्ठों पर खोजें

दस्तावेज़ के सभी पृष्ठों के लिए अवशोषक स्वीकार करें:

```csharp
document.Pages.Accept(textAbsorber);
```

## चरण 8: पाए गए टेक्स्ट के चारों ओर एक आयत बनाएं

 एक बनाने के`PdfContentEditor` पुनर्प्राप्त पाठ खंडों के माध्यम से ऑब्जेक्ट और लूप, प्रत्येक पाठ खंड के चारों ओर एक आयत बनाएं:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## चरण 9: संशोधित दस्तावेज़ सहेजें

संशोधित दस्तावेज़ सहेजें:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 प्रतिस्थापित करना सुनिश्चित करें`"SearchTextAndDrawRectangle_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट खोजें और आयत बनाएं के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// रेगुलर एक्सप्रेशन से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए टेक्स्टएब्जॉर्बर ऑब्जेक्ट बनाएं
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि पीडीएफ दस्तावेज़ में विशिष्ट पाठ की खोज कैसे करें, पाए गए पाठ के चारों ओर एक आयत कैसे बनाएं, और .NET के लिए Aspose.PDF का उपयोग करके संशोधित दस्तावेज़ को कैसे सहेजें। इस ट्यूटोरियल में प्रोजेक्ट स्थापित करने से लेकर आवश्यक कार्रवाई करने तक चरण-दर-चरण मार्गदर्शिका प्रदान की गई। अब आप टेक्स्ट में हेरफेर करने और पीडीएफ फाइलों में आयत बनाने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पाठ खोजें और आयत बनाएं" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "टेक्स्ट खोजें और आयत बनाएं" ट्यूटोरियल का उद्देश्य उपयोगकर्ताओं को .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से एक पीडीएफ दस्तावेज़ के भीतर विशिष्ट पाठ की खोज करना, पाए गए पाठ खंडों के चारों ओर आयत बनाना और संशोधित को सहेजना है। दस्तावेज़। ट्यूटोरियल प्रक्रिया के प्रत्येक चरण को स्पष्ट करने के लिए विस्तृत निर्देश और C# कोड नमूने प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में विशिष्ट पाठ के चारों ओर आयत बनाने में कैसे मदद करता है?

उ: यह ट्यूटोरियल एक पीडीएफ दस्तावेज़ के भीतर विशिष्ट पाठ खंडों के चारों ओर आयतों का पता लगाने और उन्हें बनाने के बारे में एक व्यापक मार्गदर्शिका प्रदान करता है। यह एक प्रोजेक्ट स्थापित करने, एक पीडीएफ दस्तावेज़ लोड करने, नियमित अभिव्यक्ति खोज को सक्षम करने, पाए गए पाठ खंडों के चारों ओर आयत बनाने और संशोधित पीडीएफ को सहेजने की प्रक्रिया को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल का पालन करने के लिए किन पूर्वावश्यकताओं की आवश्यकता है?

उत्तर: ट्यूटोरियल शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपको .NET लाइब्रेरी के लिए Aspose.PDF स्थापित करना होगा। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या NuGet का उपयोग करके इसे अपने प्रोजेक्ट में इंस्टॉल कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उ: अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाकर शुरुआत करें। फिर, अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें। यह आपको पीडीएफ दस्तावेज़ों में हेरफेर करने के लिए लाइब्रेरी की कार्यक्षमता का उपयोग करने में सक्षम करेगा।

#### प्रश्न: क्या मैं इस ट्यूटोरियल का उपयोग करके विशिष्ट पाठ के चारों ओर आयत बना सकता हूँ?

उ: हाँ, ट्यूटोरियल एक पीडीएफ दस्तावेज़ के भीतर विशिष्ट पाठ खंडों के चारों ओर आयत बनाने पर केंद्रित है। यह दर्शाता है कि नियमित अभिव्यक्तियों का उपयोग करके वांछित पाठ का पता कैसे लगाया जाए, पहचाने गए पाठ खंडों के चारों ओर आयतें बनाएं और संशोधित पीडीएफ को सहेजें।

#### प्रश्न: मैं उस पाठ को कैसे निर्दिष्ट कर सकता हूं जिसे मैं खोजना चाहता हूं और उसके चारों ओर आयत कैसे बना सकता हूं?

 उ: उस पाठ को निर्दिष्ट करने के लिए जिसे आप खोजना चाहते हैं और उसके चारों ओर आयत बनाना चाहते हैं, एक बनाएं`TextFragmentAbsorber` ऑब्जेक्ट बनाएं और उसका पैटर्न सेट करें`Text` पैरामीटर. डिफ़ॉल्ट पैटर्न बदलें`@"[\S]+"` अपने वांछित नियमित अभिव्यक्ति पैटर्न के साथ ट्यूटोरियल के कोड में।

#### प्रश्न: मैं टेक्स्ट के लिए रेगुलर एक्सप्रेशन खोज कैसे सक्षम करूं?

 ए: रेगुलर एक्सप्रेशन खोज को बनाकर सक्षम किया गया है`TextSearchOptions` ऑब्जेक्ट और उसका मान सेट करना`true` . इस ऑब्जेक्ट को असाइन करें`TextSearchOptions` की संपत्ति`TextFragmentAbsorber` उदाहरण। यह सुनिश्चित करता है कि पाठ खोज के दौरान नियमित अभिव्यक्ति पैटर्न का उपयोग किया जाता है।

#### प्रश्न: मैं पाए गए पाठ के चारों ओर आयत कैसे बनाऊं?

 उ: का उपयोग करके पाठ खंडों की पहचान करने के बाद`TextFragmentAbsorber` , ट्यूटोरियल इन खंडों के माध्यम से पुनरावृत्त करने के लिए एक लूप प्रदान करता है। प्रत्येक पाठ खंड के लिए, ट्यूटोरियल दर्शाता है कि इसका उपयोग करके उसके चारों ओर एक आयत कैसे बनाया जाए`DrawBox` विधि और आयत का स्वरूप निर्दिष्ट करें।

#### प्रश्न: संशोधित पीडीएफ को खींचे गए आयतों के साथ सहेजने के लिए क्या कदम हैं?

उ: वांछित पाठ खंडों के चारों ओर आयत बनाने के बाद, इसका उपयोग करें`Document` कक्षा का`Save` संशोधित दस्तावेज़ को सहेजने की विधि. ट्यूटोरियल का नमूना कोड दिखाता है कि संपादित पीडीएफ को कैसे सहेजा जाए और एक सफलता संदेश कैसे प्रदर्शित किया जाए।

#### प्रश्न: क्या मैं खींचे गए आयतों के स्वरूप को अनुकूलित कर सकता हूँ?

 उत्तर: हाँ, आप खींचे गए आयतों के स्वरूप को अनुकूलित कर सकते हैं। ट्यूटोरियल के नमूना कोड में,`DrawBox` आयत बनाने के लिए विधि का उपयोग किया जाता है। आप खींचे गए आयतों के स्वरूप को अनुकूलित करने के लिए रंग, शैली और मोटाई जैसे गुणों को संशोधित कर सकते हैं।