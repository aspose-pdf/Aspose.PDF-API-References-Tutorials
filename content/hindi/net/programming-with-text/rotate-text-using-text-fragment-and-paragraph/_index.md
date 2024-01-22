---
title: टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाएँ
linktitle: टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेक्स्ट खंड और पैराग्राफ का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 400
url: /hi/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
यह ट्यूटोरियल बताता है कि टेक्स्ट खंड और पैराग्राफ का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

 एकाधिक बनाएं`TextFragment` ऑब्जेक्ट, उनका टेक्स्ट और गुण सेट करें, और रोटेशन कोण निर्दिष्ट करें:

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

## चरण 6: पृष्ठ पर पाठ के टुकड़े जोड़ें

 बनाए गए टेक्स्ट अंशों को पृष्ठ पर जोड़कर जोड़ें`Paragraphs` संग्रह:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

 का उपयोग करके संशोधित पीडीएफ दस्तावेज़ को एक फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated3_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट को घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट प्रारंभ करें
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

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में टेक्स्ट अंशों और पैराग्राफों का उपयोग करके टेक्स्ट को घुमाने का तरीका सफलतापूर्वक सीखा है। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक चरण-दर-चरण मार्गदर्शिका प्रदान की गई है। अब आप पीडीएफ फाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य क्या है?

उ: "टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य आपको .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से एक पीडीएफ दस्तावेज़ के भीतर टेक्स्ट फ़्रैगमेंट और पैराग्राफ़ दोनों का उपयोग करके टेक्स्ट को घुमाने के लिए मार्गदर्शन करना है। ट्यूटोरियल इस कार्यक्षमता को प्राप्त करने के लिए चरण-दर-चरण निर्देश और नमूना कोड प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पिछले टेक्स्ट रोटेशन ट्यूटोरियल से किस प्रकार भिन्न है?

उ: यह ट्यूटोरियल एक पीडीएफ दस्तावेज़ के भीतर टेक्स्ट रोटेशन प्राप्त करने के लिए टेक्स्ट टुकड़े और पैराग्राफ के उपयोग को जोड़ता है। यह दर्शाता है कि पाठ के टुकड़ों को अलग-अलग कैसे घुमाया जाए और फिर उन्हें एक पृष्ठ में कैसे जोड़ा जाए`Paragraphs` अधिक व्यापक पाठ रोटेशन प्रभाव प्राप्त करने के लिए संग्रह।

#### प्रश्न: टेक्स्ट रोटेशन के लिए टेक्स्ट अंशों और पैराग्राफों का उपयोग करने के क्या फायदे हैं?

उ: पाठ के अंशों और पैराग्राफों का एक साथ उपयोग करने से पाठ रोटेशन में अधिक लचीलापन मिलता है। पाठ के टुकड़े व्यक्तिगत रोटेशन और फ़ॉर्मेटिंग सेटिंग्स को सक्षम करते हैं, जबकि पैराग्राफ एक पृष्ठ के भीतर पाठ के टुकड़ों को व्यवस्थित करने और स्थिति देने के लिए संरचना प्रदान करते हैं।

#### प्रश्न: क्या मैं एक ही पैराग्राफ के भीतर अलग-अलग पाठ खंडों पर अलग-अलग रोटेशन कोण लागू कर सकता हूं?

 उत्तर: हां, आप अलग-अलग रोटेशन कोणों को अलग-अलग पर लागू कर सकते हैं`TextFragment` एक ही अनुच्छेद के अंतर्गत वस्तुएँ। प्रत्येक पाठ खंड का अपना घूर्णन कोण निर्दिष्ट किया जा सकता है`TextState.Rotation` संपत्ति।

#### प्रश्न: क्या इस पद्धति का उपयोग करके जटिल टेक्स्ट रोटेशन प्रभाव प्राप्त करना संभव है?

उत्तर: हां, पाठ के टुकड़ों को विभिन्न घूर्णन कोणों के साथ जोड़कर और उन्हें पैराग्राफ के भीतर व्यवस्थित करके, आप अपने पीडीएफ दस्तावेजों की दृश्य अपील को बढ़ाते हुए, जटिल और अनुकूलित पाठ रोटेशन प्रभाव प्राप्त कर सकते हैं।

#### प्रश्न: पाठ के अंशों और पैराग्राफों का उपयोग करके पाठ को घुमाने में कौन से चरण शामिल हैं?

ए: चरणों में शामिल हैं:

1. एक नया C# प्रोजेक्ट बनाकर और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़कर प्रोजेक्ट सेट करना।
2. पीडीएफ दस्तावेज़ बनाना और एक पेज जोड़ना।
3. पाठ के टुकड़े बनाना, उनके गुण निर्धारित करना और घूर्णन कोण निर्दिष्ट करना।
4.  का उपयोग करके पृष्ठ पर पाठ के टुकड़े जोड़ना`Paragraphs` संग्रह।
5. संशोधित पीडीएफ दस्तावेज़ सहेजा जा रहा है।

#### प्रश्न: क्या मैं पूरे अनुच्छेदों में रोटेशन लागू कर सकता हूँ?

 उत्तर: हां, आप इसे सेट करके पूरे पैराग्राफ पर रोटेशन लागू कर सकते हैं`TextState.Rotation` अनुच्छेद की ही संपत्ति. यह उस अनुच्छेद के भीतर सभी पाठ अंशों को घुमाएगा।