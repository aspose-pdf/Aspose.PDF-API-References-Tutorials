---
title: पीडीएफ फ़ाइल में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाएँ
linktitle: पीडीएफ फ़ाइल में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट अंशों का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 390
url: /hi/net/programming-with-text/rotate-text-using-text-fragment/
---
यह ट्यूटोरियल बताता है कि पीडीएफ फ़ाइल में टेक्स्ट अंशों का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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
using Aspose.Pdf.Text.TextBuilder;
```

## चरण 3: पीडीएफ दस्तावेज़ बनाएं

 को आरंभ करें`Document` नया पीडीएफ दस्तावेज़ बनाने के लिए ऑब्जेक्ट:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 4: एक पेज जोड़ें

 का उपयोग करके दस्तावेज़ से एक विशेष पृष्ठ प्राप्त करें`Pages.Add()` तरीका:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## चरण 5: पाठ के टुकड़े बनाएँ

 एकाधिक बनाएं`TextFragment` ऑब्जेक्ट, उनका टेक्स्ट और गुण सेट करें, और पृष्ठ पर उनकी स्थिति निर्दिष्ट करें:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

पाठ, स्थिति और अन्य गुणों को इच्छानुसार समायोजित करें।

## चरण 6: एक टेक्स्टबिल्डर बनाएं और टेक्स्ट टुकड़े जोड़ें

 एक बनाने के`TextBuilder` ऑब्जेक्ट का उपयोग करना`pdfPage` और पाठ के अंशों को पीडीएफ पेज पर जोड़ें:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

 का उपयोग करके संशोधित पीडीएफ दस्तावेज़ को एक फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated1_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट प्रारंभ करें
Document pdfDocument = new Document();
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = (Page)pdfDocument.Pages.Add();
// पाठ खंड बनाएँ
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// पाठ गुण सेट करें
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// घुमाया हुआ पाठ खंड बनाएं
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// पाठ गुण सेट करें
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// घुमाया हुआ पाठ खंड बनाएं
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// पाठ गुण सेट करें
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// टेक्स्टबिल्डर ऑब्जेक्ट बनाएं
TextBuilder textBuilder = new TextBuilder(pdfPage);
// पाठ खंड को पीडीएफ पेज पर जोड़ें
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेक्स्ट अंशों का उपयोग करके टेक्स्ट को घुमाना सफलतापूर्वक सीख लिया है। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक चरण-दर-चरण मार्गदर्शिका प्रदान की गई है। अब आप पीडीएफ फाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य क्या है?

उ: "टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य पीडीएफ दस्तावेज़ में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करना है। ट्यूटोरियल इस कार्यक्षमता को प्राप्त करने के लिए चरण-दर-चरण निर्देश और नमूना कोड प्रदान करता है।

#### प्रश्न: "पाठ अंशों का उपयोग करके पाठ को घुमाना" से क्या तात्पर्य है?

उ: पाठ अंशों का उपयोग करके पाठ को घुमाना Aspose.PDF लाइब्रेरी का उपयोग करके एक पीडीएफ दस्तावेज़ के भीतर अलग-अलग पाठ अंशों पर रोटेशन लागू करने की क्षमता को संदर्भित करता है। यह तकनीक आपको पीडीएफ सामग्री के भीतर विभिन्न कोणों या स्थितियों पर पाठ के अभिविन्यास को नियंत्रित करने की अनुमति देती है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में पाठ अंशों को घुमाना क्यों चाहूंगा?

उ: पीडीएफ दस्तावेज़ में पाठ के टुकड़ों को घुमाना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे विशिष्ट सामग्री पर ज़ोर देना, कलात्मक डिज़ाइन बनाना, या लेआउट और पठनीयता में सुधार करना।

#### प्रश्न: मैं ट्यूटोरियल के लिए प्रोजेक्ट कैसे सेट करूँ?

उत्तर: परियोजना स्थापित करने के लिए:

1. अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।
3. अपनी C# फ़ाइल में आवश्यक उपयोग निर्देश जोड़ें।

#### प्रश्न: मैं एक नया पीडीएफ दस्तावेज़ कैसे बना सकता हूँ?

 ए: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, इनिशियलाइज़ करें`Document`Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। आप पीडीएफ में पेज और सामग्री जोड़ने के लिए इस ऑब्जेक्ट का उपयोग कर सकते हैं।

#### प्रश्न: मैं टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट फ़्रैगमेंट को कैसे घुमा सकता हूँ?

उ: पाठ अंशों का उपयोग करके पाठ अंशों को घुमाने के लिए:

1.  बनाएं`TextFragment` वस्तुएं.
2. पाठ अंशों का पाठ और गुण सेट करें।
3. पृष्ठ पर पाठ अंशों की स्थिति निर्दिष्ट करें।
4.  का उपयोग करके घूर्णन कोण सेट करें`TextState.Rotation` पाठ अंशों की संपत्ति.
5.  एक बनाने के`TextBuilder`ऑब्जेक्ट करें और पाठ के अंशों को पीडीएफ पेज पर जोड़ें।

#### प्रश्न: क्या मैं अलग-अलग पाठ अंशों पर अलग-अलग रोटेशन कोण लागू कर सकता हूं?

 उत्तर: हां, आप अलग-अलग रोटेशन कोणों को अलग-अलग पर लागू कर सकते हैं`TextFragment` वस्तुएं. प्रत्येक पाठ खंड का अपना घूर्णन कोण निर्दिष्ट किया जा सकता है`TextState.Rotation` संपत्ति।

#### प्रश्न: मैं घुमाए गए पाठ अंशों के साथ पीडीएफ दस्तावेज़ को कैसे सहेज सकता हूं?

 उ: घुमाए गए पाठ अंशों के साथ पीडीएफ दस्तावेज़ को सहेजने के लिए, इसका उपयोग करें`Save` की विधि`Document` ऑब्जेक्ट बनाएं और वांछित आउटपुट फ़ाइल पथ और नाम प्रदान करें।