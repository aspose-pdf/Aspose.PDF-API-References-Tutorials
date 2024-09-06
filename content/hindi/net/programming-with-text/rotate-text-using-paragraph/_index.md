---
title: पीडीएफ फाइल में पैराग्राफ का उपयोग करके टेक्स्ट घुमाएं
linktitle: पीडीएफ फाइल में पैराग्राफ का उपयोग करके टेक्स्ट घुमाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 380
url: /hi/net/programming-with-text/rotate-text-using-paragraph/
---
यह ट्यूटोरियल बताता है कि पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

## चरण 5: पाठ पैराग्राफ़ बनाएँ

 एक बनाने के`TextParagraph` ऑब्जेक्ट और पृष्ठ पर इसकी स्थिति निर्धारित करें:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

अपनी आवश्यकताओं के अनुसार स्थिति मान समायोजित करें।

## चरण 6: पाठ अंश बनाएँ और कॉन्फ़िगर करें

 एकाधिक बनाएँ`TextFragment` ऑब्जेक्ट्स और उनके पाठ और गुण सेट करें:

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

## चरण 7: पैराग्राफ़ में पाठ अंश जोड़ें

 बनाए गए पाठ अंशों को पैराग्राफ में जोड़ें`AppendLine` तरीका:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## चरण 8: एक टेक्स्टबिल्डर बनाएं और पैराग्राफ जोड़ें

 एक बनाने के`TextBuilder` वस्तु का उपयोग कर`pdfPage` और पाठ पैराग्राफ को पीडीएफ पृष्ठ में जोड़ें:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## चरण 9: पीडीएफ दस्तावेज़ सहेजें

 संशोधित PDF दस्तावेज़ को फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated2_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ.

### .NET के लिए Aspose.PDF का उपयोग करके पैराग्राफ का उपयोग करके टेक्स्ट घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट आरंभ करें
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
// पैराग्राफ़ में पाठ अंश जोड़ें
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// TextBuilder ऑब्जेक्ट बनाएँ
TextBuilder textBuilder = new TextBuilder(pdfPage);
// पाठ पैराग्राफ को पीडीएफ पृष्ठ में जोड़ें
textBuilder.AppendParagraph(paragraph);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में पैराग्राफ़ का उपयोग करके टेक्स्ट को कैसे घुमाया जाए। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक, चरण-दर-चरण मार्गदर्शन प्रदान किया गया है। अब आप PDF फ़ाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पैराग्राफ का उपयोग करके टेक्स्ट घुमाएं" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पैराग्राफ का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य आपको PDF दस्तावेज़ में टेक्स्ट पैराग्राफ़ का उपयोग करके टेक्स्ट घुमाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। ट्यूटोरियल इस कार्यक्षमता को प्राप्त करने के लिए चरण-दर-चरण निर्देश और नमूना कोड प्रदान करता है।

#### प्रश्न: "पैराग्राफ का उपयोग करके पाठ को घुमाने" का क्या अर्थ है?

उत्तर: पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाना, टेक्स्ट पैराग्राफ़ का उपयोग करके PDF दस्तावेज़ के भीतर टेक्स्ट को घुमाने की क्षमता को संदर्भित करता है। यह तकनीक आपको PDF सामग्री के भीतर टेक्स्ट को अलग-अलग कोणों या स्थितियों पर उन्मुख करने की अनुमति देती है।

#### प्रश्न: मैं PDF दस्तावेज़ में पाठ को घुमाना क्यों चाहूंगा?

उत्तर: पीडीएफ दस्तावेज़ में पाठ को घुमाना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे विशिष्ट सामग्री पर जोर देना, कलात्मक डिज़ाइन बनाना, या लेआउट और पठनीयता में सुधार करना।

#### प्रश्न: मैं एक नया पीडीएफ दस्तावेज़ कैसे बना सकता हूं?

 उत्तर: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, एक प्रारंभ करें`Document`Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। आप इस ऑब्जेक्ट का उपयोग PDF में पेज और सामग्री जोड़ने के लिए कर सकते हैं।

#### प्रश्न: मैं पैराग्राफ़ का उपयोग करके टेक्स्ट को कैसे घुमाऊं?

उत्तर: पैराग्राफ़ का उपयोग करके पाठ को घुमाने के लिए:

1.  एक बनाने के`TextParagraph` वस्तु।
2.  बनाएं`TextFragment` इच्छित पाठ और घूर्णन कोण वाली वस्तुएं।
3. पाठ अंशों को पाठ पैराग्राफ में जोड़ें।
4.  एक बनाने के`TextBuilder` ऑब्जेक्ट और पाठ पैराग्राफ को एक विशिष्ट पीडीएफ पेज में जोड़ें।

#### प्रश्न: क्या मैं अलग-अलग पाठ अंशों के घूर्णन कोण को नियंत्रित कर सकता हूँ?

 उत्तर: हां, आप व्यक्तिगत रोटेशन कोण को नियंत्रित कर सकते हैं`TextFragment` वस्तुओं को सेट करके`TextState.Rotation` संपत्ति। सकारात्मक मान दक्षिणावर्त घूर्णन को इंगित करते हैं, जबकि नकारात्मक मान वामावर्त घूर्णन को इंगित करते हैं।

#### प्रश्न: क्या मैं एक ही पैराग्राफ के विभिन्न पाठ अंशों पर अलग-अलग रोटेशन कोण लागू कर सकता हूँ?

 उत्तर: हां, आप अलग-अलग जगहों पर अलग-अलग रोटेशन एंगल लागू कर सकते हैं।`TextFragment` एक ही पैराग्राफ़ के भीतर ऑब्जेक्ट्स को सेट करके`TextState.Rotation` प्रत्येक खंड की संपत्ति तदनुसार।

#### प्रश्न: मैं घुमाए गए पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

उत्तर: घुमाए गए पीडीएफ दस्तावेज़ को सहेजने के लिए, का उपयोग करें`Save` की विधि`Document` ऑब्जेक्ट और वांछित आउटपुट फ़ाइल पथ और नाम प्रदान करें।