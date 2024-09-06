---
title: टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट घुमाएँ
linktitle: टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट घुमाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेक्स्ट अंश और पैराग्राफ का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 400
url: /hi/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
यह ट्यूटोरियल बताता है कि टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

 एकाधिक बनाएँ`TextFragment` ऑब्जेक्ट्स, उनका टेक्स्ट और गुण सेट करें, और रोटेशन कोण निर्दिष्ट करें:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

पाठ, घूर्णन कोण और अन्य गुणों को इच्छानुसार समायोजित करें।

## चरण 6: पृष्ठ पर पाठ अंश जोड़ें

 बनाए गए पाठ अंशों को पृष्ठ पर जोड़कर जोड़ें`Paragraphs` संग्रह:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

 संशोधित PDF दस्तावेज़ को फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated3_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ.

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट आरंभ करें
Document pdfDocument = new Document();
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = (Page)pdfDocument.Pages.Add();
// पाठ खंड बनाएँ
TextFragment textFragment1 = new TextFragment("main text");
// पाठ गुण सेट करें
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// पाठ खंड बनाएँ
TextFragment textFragment2 = new TextFragment("rotated text");
// पाठ गुण सेट करें
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// रोटेशन सेट करें
textFragment2.TextState.Rotation = 315;
// पाठ खंड बनाएँ
TextFragment textFragment3 = new TextFragment("rotated text");
// पाठ गुण सेट करें
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// रोटेशन सेट करें
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेक्स्ट अंशों और पैराग्राफ़ का उपयोग करके टेक्स्ट को कैसे घुमाया जाए। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक, चरण-दर-चरण मार्गदर्शिका प्रदान की गई है। अब आप PDF फ़ाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट फ्रेगमेंट और पैराग्राफ का उपयोग करके टेक्स्ट घुमाएं" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाएँ" ट्यूटोरियल का उद्देश्य आपको .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ दोनों का उपयोग करके टेक्स्ट को घुमाने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। ट्यूटोरियल इस कार्यक्षमता को प्राप्त करने के लिए चरण-दर-चरण निर्देश और नमूना कोड प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पिछले टेक्स्ट रोटेशन ट्यूटोरियल से किस प्रकार भिन्न है?

उत्तर: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में टेक्स्ट रोटेशन प्राप्त करने के लिए टेक्स्ट अंशों और पैराग्राफ़ के उपयोग को जोड़ता है। यह दर्शाता है कि टेक्स्ट अंशों को अलग-अलग कैसे घुमाया जाए और फिर उन्हें पेज के टेक्स्ट में कैसे जोड़ा जाए।`Paragraphs` अधिक व्यापक पाठ रोटेशन प्रभाव प्राप्त करने के लिए संग्रह को संशोधित किया जा सकता है।

#### प्रश्न: पाठ रोटेशन के लिए पाठ अंशों और पैराग्राफों का उपयोग करने के क्या लाभ हैं?

उत्तर: टेक्स्ट अंशों और पैराग्राफ़ों का एक साथ उपयोग करने से टेक्स्ट रोटेशन में अधिक लचीलापन मिलता है। टेक्स्ट अंश अलग-अलग रोटेशन और फ़ॉर्मेटिंग सेटिंग सक्षम करते हैं, जबकि पैराग्राफ़ किसी पृष्ठ के भीतर टेक्स्ट अंशों को व्यवस्थित करने और उनकी स्थिति निर्धारित करने के लिए संरचना प्रदान करते हैं।

#### प्रश्न: क्या मैं एक ही पैराग्राफ के विभिन्न पाठ अंशों पर अलग-अलग रोटेशन कोण लागू कर सकता हूँ?

 उत्तर: हां, आप अलग-अलग जगहों पर अलग-अलग रोटेशन एंगल लागू कर सकते हैं।`TextFragment` एक ही पैराग्राफ़ के भीतर ऑब्जेक्ट्स। प्रत्येक टेक्स्ट फ़्रैगमेंट का अपना रोटेशन एंगल हो सकता है जिसे का उपयोग करके निर्दिष्ट किया जा सकता है`TextState.Rotation` संपत्ति।

#### प्रश्न: क्या इस विधि का उपयोग करके जटिल पाठ रोटेशन प्रभाव प्राप्त करना संभव है?

उत्तर: हां, विभिन्न घूर्णन कोणों के साथ पाठ अंशों को संयोजित करके और उन्हें पैराग्राफों के भीतर व्यवस्थित करके, आप जटिल और अनुकूलित पाठ घूर्णन प्रभाव प्राप्त कर सकते हैं, जिससे आपके पीडीएफ दस्तावेजों की दृश्य अपील बढ़ जाती है।

#### प्रश्न: पाठ अंशों और पैराग्राफों का उपयोग करके पाठ को घुमाने में क्या चरण शामिल हैं?

उत्तर: इसमें निम्नलिखित चरण शामिल हैं:

1. एक नया C# प्रोजेक्ट बनाकर और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़कर प्रोजेक्ट की स्थापना करना।
2. पीडीएफ दस्तावेज़ बनाना और एक पृष्ठ जोड़ना।
3. पाठ खंड बनाना, उनके गुणधर्म निर्धारित करना, तथा घूर्णन कोण निर्दिष्ट करना।
4.  पृष्ठ पर पाठ अंश जोड़ना`Paragraphs` संग्रह।
5. संशोधित PDF दस्तावेज़ को सहेजना.

#### प्रश्न: क्या मैं संपूर्ण पैराग्राफ पर रोटेशन लागू कर सकता हूं?

 उत्तर: हां, आप सेटिंग करके पूरे पैराग्राफ पर रोटेशन लागू कर सकते हैं।`TextState.Rotation` पैराग्राफ़ की अपनी प्रॉपर्टी पर क्लिक करें। इससे उस पैराग्राफ़ के सभी टेक्स्ट फ़्रैगमेंट घूम जाएँगे।