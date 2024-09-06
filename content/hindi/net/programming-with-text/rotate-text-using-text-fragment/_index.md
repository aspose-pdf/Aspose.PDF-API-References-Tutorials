---
title: पीडीएफ फाइल में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट घुमाएँ
linktitle: पीडीएफ फाइल में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट घुमाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट अंशों का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 390
url: /hi/net/programming-with-text/rotate-text-using-text-fragment/
---
यह ट्यूटोरियल बताता है कि PDF फ़ाइल में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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
using Aspose.Pdf.Text.TextBuilder;
```

## चरण 3: पीडीएफ दस्तावेज़ बनाएँ

 आरंभ करें`Document` नया PDF दस्तावेज़ बनाने के लिए ऑब्जेक्ट:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 4: पेज जोड़ें

 दस्तावेज़ से कोई विशेष पृष्ठ प्राप्त करने के लिए निम्न का उपयोग करें:`Pages.Add()` तरीका:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## चरण 5: पाठ अंश बनाएँ

 एकाधिक बनाएँ`TextFragment` ऑब्जेक्ट्स, उनका टेक्स्ट और गुण सेट करें, और पृष्ठ पर उनकी स्थिति निर्दिष्ट करें:

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

## चरण 6: एक टेक्स्टबिल्डर बनाएं और टेक्स्ट अंश जोड़ें

 एक बनाने के`TextBuilder` वस्तु का उपयोग कर`pdfPage` और पाठ अंशों को पीडीएफ पृष्ठ में जोड़ें:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

 संशोधित PDF दस्तावेज़ को फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated1_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ.

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट आरंभ करें
Document pdfDocument = new Document();
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = (Page)pdfDocument.Pages.Add();
// पाठ खंड बनाएँ
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// पाठ गुण सेट करें
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// घुमाए गए पाठ खंड बनाएँ
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// पाठ गुण सेट करें
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// घुमाए गए पाठ खंड बनाएँ
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// पाठ गुण सेट करें
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// टेक्स्टबिल्डर ऑब्जेक्ट बनाएं
TextBuilder textBuilder = new TextBuilder(pdfPage);
// पाठ अंश को PDF पृष्ठ पर जोड़ें
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेक्स्ट अंशों का उपयोग करके टेक्स्ट को कैसे घुमाया जाए। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक, चरण-दर-चरण मार्गदर्शन प्रदान किया गया है। अब आप PDF फ़ाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट फ्रेगमेंट का उपयोग करके टेक्स्ट घुमाएं" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाएँ" ट्यूटोरियल का उद्देश्य आपको PDF दस्तावेज़ में टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। ट्यूटोरियल इस कार्यक्षमता को प्राप्त करने के लिए चरण-दर-चरण निर्देश और नमूना कोड प्रदान करता है।

#### प्रश्न: "पाठ अंशों का उपयोग करके पाठ को घुमाना" से क्या अभिप्राय है?

उत्तर: टेक्स्ट फ़्रैगमेंट का उपयोग करके टेक्स्ट को घुमाना, Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ के भीतर अलग-अलग टेक्स्ट फ़्रैगमेंट पर रोटेशन लागू करने की क्षमता को संदर्भित करता है। यह तकनीक आपको PDF सामग्री के भीतर अलग-अलग कोणों या स्थितियों पर टेक्स्ट के ओरिएंटेशन को नियंत्रित करने की अनुमति देती है।

#### प्रश्न: मैं PDF दस्तावेज़ में पाठ अंशों को घुमाना क्यों चाहूंगा?

उत्तर: पीडीएफ दस्तावेज़ में पाठ अंशों को घुमाना विभिन्न प्रयोजनों के लिए उपयोगी हो सकता है, जैसे विशिष्ट सामग्री पर जोर देना, कलात्मक डिजाइन बनाना, या लेआउट और पठनीयता में सुधार करना।

#### प्रश्न: मैं ट्यूटोरियल के लिए प्रोजेक्ट कैसे सेट करूँ?

उत्तर: परियोजना स्थापित करने के लिए:

1. अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।
3. अपनी C# फ़ाइल में आवश्यक using निर्देश जोड़ें।

#### प्रश्न: मैं एक नया पीडीएफ दस्तावेज़ कैसे बना सकता हूं?

 उत्तर: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, एक प्रारंभ करें`Document`Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। आप इस ऑब्जेक्ट का उपयोग PDF में पेज और सामग्री जोड़ने के लिए कर सकते हैं।

#### प्रश्न: मैं टेक्स्ट अंशों का उपयोग करके टेक्स्ट अंशों को कैसे घुमा सकता हूँ?

उत्तर: पाठ अंशों का उपयोग करके पाठ अंशों को घुमाने के लिए:

1.  बनाएं`TextFragment` वस्तुएं.
2. पाठ अंशों का पाठ और गुणधर्म सेट करें.
3. पृष्ठ पर पाठ अंशों की स्थिति निर्दिष्ट करें.
4.  रोटेशन कोण को सेट करने के लिए निम्न का उपयोग करें:`TextState.Rotation` पाठ अंशों की संपत्ति.
5.  एक बनाने के`TextBuilder`ऑब्जेक्ट पर क्लिक करें और पाठ अंशों को पीडीएफ पृष्ठ में जोड़ें।

#### प्रश्न: क्या मैं अलग-अलग पाठ अंशों पर अलग-अलग घूर्णन कोण लागू कर सकता हूँ?

 उत्तर: हां, आप अलग-अलग जगहों पर अलग-अलग रोटेशन एंगल लागू कर सकते हैं।`TextFragment` ऑब्जेक्ट्स। प्रत्येक टेक्स्ट फ़्रैगमेंट का अपना रोटेशन एंगल हो सकता है जिसे का उपयोग करके निर्दिष्ट किया जा सकता है`TextState.Rotation` संपत्ति।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को घुमाए गए पाठ अंशों के साथ कैसे सहेज सकता हूं?

 उत्तर: पीडीएफ दस्तावेज़ को घुमाए गए पाठ अंशों के साथ सहेजने के लिए, का उपयोग करें`Save` की विधि`Document` ऑब्जेक्ट और वांछित आउटपुट फ़ाइल पथ और नाम प्रदान करें।