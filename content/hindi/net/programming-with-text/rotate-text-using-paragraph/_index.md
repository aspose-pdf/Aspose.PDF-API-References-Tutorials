---
title: पीडीएफ फाइल में पैराग्राफ का उपयोग करके टेक्स्ट को घुमाएँ
linktitle: पीडीएफ फाइल में पैराग्राफ का उपयोग करके टेक्स्ट को घुमाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में पैराग्राफ का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 380
url: /hi/net/programming-with-text/rotate-text-using-paragraph/
---
यह ट्यूटोरियल बताता है कि पैराग्राफ का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

## चरण 5: टेक्स्ट पैराग्राफ़ बनाएं

 एक बनाने के`TextParagraph` ऑब्जेक्ट करें और पृष्ठ पर उसकी स्थिति निर्धारित करें:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

अपनी आवश्यकताओं के अनुसार स्थिति मूल्यों को समायोजित करें।

## चरण 6: टेक्स्ट टुकड़े बनाएं और कॉन्फ़िगर करें

 एकाधिक बनाएं`TextFragment` ऑब्जेक्ट्स और उनके टेक्स्ट और गुण सेट करें:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

पाठ और अन्य गुणों को इच्छानुसार समायोजित करें।

## चरण 7: पैराग्राफ में पाठ के टुकड़े जोड़ें

 का उपयोग करके बनाए गए टेक्स्ट अंशों को पैराग्राफ में जोड़ें`AppendLine` तरीका:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## चरण 8: एक टेक्स्टबिल्डर बनाएं और पैराग्राफ जोड़ें

 एक बनाने के`TextBuilder` ऑब्जेक्ट का उपयोग करना`pdfPage` और टेक्स्ट पैराग्राफ को पीडीएफ पेज पर जोड़ें:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## चरण 9: पीडीएफ दस्तावेज़ सहेजें

 का उपयोग करके संशोधित पीडीएफ दस्तावेज़ को एक फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated2_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ।

### .NET के लिए Aspose.PDF का उपयोग करके पैराग्राफ का उपयोग करके टेक्स्ट को घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट प्रारंभ करें
Document pdfDocument = new Document();
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// पाठ खंड बनाएँ
TextFragment textFragment1 = new TextFragment("rotated text");
// पाठ गुण सेट करें
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// रोटेशन सेट करें
textFragment1.TextState.Rotation = 45;
// पाठ खंड बनाएँ
TextFragment textFragment2 = new TextFragment("main text");
// पाठ गुण सेट करें
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// पाठ खंड बनाएँ
TextFragment textFragment3 = new TextFragment("another rotated text");
// पाठ गुण सेट करें
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// रोटेशन सेट करें
textFragment3.TextState.Rotation = -45;
// पाठ के अंशों को अनुच्छेद में जोड़ें
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// टेक्स्टबिल्डर ऑब्जेक्ट बनाएं
TextBuilder textBuilder = new TextBuilder(pdfPage);
// टेक्स्ट पैराग्राफ को पीडीएफ पेज पर जोड़ें
textBuilder.AppendParagraph(paragraph);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में पैराग्राफ का उपयोग करके टेक्स्ट को घुमाना सफलतापूर्वक सीख लिया है। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक चरण-दर-चरण मार्गदर्शिका प्रदान की गई है। अब आप पीडीएफ फाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पैराग्राफ का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पैराग्राफ का उपयोग करके टेक्स्ट घुमाएं" ट्यूटोरियल का उद्देश्य पीडीएफ दस्तावेज़ में टेक्स्ट पैराग्राफ का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करना है। ट्यूटोरियल इस कार्यक्षमता को प्राप्त करने के लिए चरण-दर-चरण निर्देश और नमूना कोड प्रदान करता है।

#### प्रश्न: "पैराग्राफ का उपयोग करके पाठ को घुमाना" से क्या तात्पर्य है?

ए: पैराग्राफ का उपयोग करके टेक्स्ट को घुमाने से तात्पर्य टेक्स्ट पैराग्राफ का उपयोग करके पीडीएफ दस्तावेज़ के भीतर टेक्स्ट में रोटेशन लागू करने की क्षमता से है। यह तकनीक आपको पीडीएफ सामग्री के भीतर विभिन्न कोणों या स्थितियों पर पाठ को उन्मुख करने की अनुमति देती है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में टेक्स्ट को घुमाना क्यों चाहूंगा?

उ: पीडीएफ दस्तावेज़ में पाठ को घुमाना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे विशिष्ट सामग्री पर ज़ोर देना, कलात्मक डिज़ाइन बनाना, या लेआउट और पठनीयता में सुधार करना।

#### प्रश्न: मैं एक नया पीडीएफ दस्तावेज़ कैसे बना सकता हूँ?

 ए: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, इनिशियलाइज़ करें`Document`Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। आप पीडीएफ में पेज और सामग्री जोड़ने के लिए इस ऑब्जेक्ट का उपयोग कर सकते हैं।

#### प्रश्न: मैं अनुच्छेदों का उपयोग करके पाठ को कैसे घुमा सकता हूँ?

ए: पैराग्राफ का उपयोग करके पाठ को घुमाने के लिए:

1.  एक बनाने के`TextParagraph` वस्तु।
2.  बनाएं`TextFragment` वांछित पाठ और घूर्णन कोण वाली वस्तुएं।
3. पाठ के अंशों को पाठ पैराग्राफ में जोड़ें।
4.  एक बनाने के`TextBuilder` ऑब्जेक्ट करें और टेक्स्ट पैराग्राफ को एक विशिष्ट पीडीएफ पेज पर जोड़ें।

#### प्रश्न: क्या मैं अलग-अलग पाठ अंशों के घूर्णन कोण को नियंत्रित कर सकता हूँ?

 उत्तर: हाँ, आप व्यक्ति के घूर्णन कोण को नियंत्रित कर सकते हैं`TextFragment` ऑब्जेक्ट सेट करके`TextState.Rotation` संपत्ति। सकारात्मक मान दक्षिणावर्त घुमाव को दर्शाते हैं, जबकि नकारात्मक मान वामावर्त घुमाव को दर्शाते हैं।

#### प्रश्न: क्या मैं एक ही पैराग्राफ के भीतर अलग-अलग पाठ खंडों पर अलग-अलग रोटेशन कोण लागू कर सकता हूं?

 उत्तर: हां, आप अलग-अलग रोटेशन कोणों को अलग-अलग पर लागू कर सकते हैं`TextFragment` को सेट करके एक ही पैराग्राफ के भीतर ऑब्जेक्ट`TextState.Rotation` तदनुसार प्रत्येक टुकड़े की संपत्ति।

#### प्रश्न: मैं घुमाए गए पीडीएफ दस्तावेज़ को कैसे सहेजूं?

उ: घुमाए गए पीडीएफ दस्तावेज़ को सहेजने के लिए, इसका उपयोग करें`Save` की विधि`Document` ऑब्जेक्ट बनाएं और वांछित आउटपुट फ़ाइल पथ और नाम प्रदान करें।