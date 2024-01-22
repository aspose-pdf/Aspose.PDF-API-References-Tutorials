---
title: पीडीएफ फाइल में टेक्स्ट पैराग्राफ और बिल्डर का उपयोग करके टेक्स्ट को घुमाएं
linktitle: पीडीएफ फाइल में टेक्स्ट पैराग्राफ और बिल्डर का उपयोग करके टेक्स्ट को घुमाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में टेक्स्ट पैराग्राफ और बिल्डर का उपयोग करके टेक्स्ट को घुमाना सीखें।
type: docs
weight: 410
url: /hi/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
यह ट्यूटोरियल बताता है कि पीडीएफ फाइल में टेक्स्ट पैराग्राफ और बिल्डर्स का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

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

## चरण 5: टेक्स्ट पैराग्राफ बनाएं और घुमाएँ

 एक बनाने के`for` अलग-अलग घुमावों के साथ कई टेक्स्ट पैराग्राफ उत्पन्न करने के लिए लूप:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

अपनी आवश्यकताओं के अनुसार स्थिति और रोटेशन मानों को समायोजित करें।

## चरण 6: टेक्स्ट टुकड़े बनाएं और कॉन्फ़िगर करें

 एकाधिक बनाएं`TextFragment` ऑब्जेक्ट, उनका टेक्स्ट और गुण सेट करें:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
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
}
```

## चरण 9: पीडीएफ दस्तावेज़ सहेजें

 का उपयोग करके संशोधित पीडीएफ दस्तावेज़ को एक फ़ाइल में सहेजें`Save` तरीका:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"TextFragmentTests_Rotated4_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट पैराग्राफ और बिल्डर का उपयोग करके टेक्स्ट को घुमाने के लिए नमूना स्रोत कोड 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट प्रारंभ करें
Document pdfDocument = new Document();
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// रोटेशन निर्दिष्ट करें
	paragraph.Rotation = i * 90 + 45;
	// पाठ खंड बनाएँ
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// पाठ खंड बनाएँ
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// पाठ खंड बनाएँ
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// पाठ गुण सेट करें
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// पाठ खंड बनाएँ
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// पाठ गुण सेट करें
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// टेक्स्टबिल्डर ऑब्जेक्ट बनाएं
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// पाठ खंड को पीडीएफ पेज पर जोड़ें
	textBuilder.AppendParagraph(paragraph);
}
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में टेक्स्ट पैराग्राफ और बिल्डर्स का उपयोग करके टेक्स्ट को घुमाने का तरीका सफलतापूर्वक सीखा है। इस ट्यूटोरियल में दस्तावेज़ बनाने से लेकर संशोधित संस्करण को सहेजने तक चरण-दर-चरण मार्गदर्शिका प्रदान की गई है। अब आप पीडीएफ फाइलों में टेक्स्ट रोटेशन में हेरफेर करने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट पैराग्राफ और बिल्डर का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल का उद्देश्य क्या है?

उ: "टेक्स्ट पैराग्राफ और बिल्डर का उपयोग करके टेक्स्ट घुमाएँ" ट्यूटोरियल एक पीडीएफ दस्तावेज़ के भीतर टेक्स्ट पैराग्राफ और बिल्डरों का उपयोग करके टेक्स्ट को घुमाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने के तरीके पर एक व्यापक गाइड प्रदान करता है। ट्यूटोरियल चरण-दर-चरण निर्देश प्रदर्शित करता है और इसमें पैराग्राफ और कस्टम फ़ॉर्मेटिंग के साथ टेक्स्ट रोटेशन प्राप्त करने के लिए नमूना C# कोड शामिल है।

#### प्रश्न: यह ट्यूटोरियल पिछले टेक्स्ट रोटेशन ट्यूटोरियल से किस प्रकार भिन्न है?

उत्तर: पिछले ट्यूटोरियल के विपरीत, यह ट्यूटोरियल अधिक उन्नत टेक्स्ट रोटेशन प्रभाव प्राप्त करने के लिए टेक्स्ट पैराग्राफ, बिल्डर्स और रोटेशन कोणों के उपयोग को जोड़ता है। यह दर्शाता है कि अलग-अलग रोटेशन कोणों के साथ एकाधिक टेक्स्ट पैराग्राफ कैसे उत्पन्न करें और व्यक्तिगत टेक्स्ट टुकड़ों पर कस्टम फ़ॉर्मेटिंग कैसे लागू करें।

#### प्रश्न: टेक्स्ट रोटेशन के लिए टेक्स्ट पैराग्राफ और बिल्डर्स का उपयोग करने का क्या महत्व है?

उ: टेक्स्ट पैराग्राफ और बिल्डरों का उपयोग करने से टेक्स्ट रोटेशन और फ़ॉर्मेटिंग पर नियंत्रण बढ़ाया जा सकता है। टेक्स्ट पैराग्राफ, टेक्स्ट अंशों को व्यवस्थित करने का एक संरचित तरीका प्रदान करते हैं, जबकि बिल्डर्स पीडीएफ दस्तावेज़ के भीतर टेक्स्ट सामग्री के निर्माण और हेरफेर की सुविधा प्रदान करते हैं।

#### प्रश्न: क्या मैं प्रत्येक पाठ पैराग्राफ पर अलग-अलग रोटेशन कोण लागू कर सकता हूं?

 उत्तर: हां, आप इसे सेट करके प्रत्येक टेक्स्ट पैराग्राफ पर अलग-अलग रोटेशन कोण लागू कर सकते हैं`Rotation` की संपत्ति`TextParagraph` वस्तु। यह आपको पीडीएफ दस्तावेज़ के भीतर विविध और गतिशील टेक्स्ट रोटेशन प्रभाव बनाने की अनुमति देता है।

#### प्रश्न: मैं पाठ पैराग्राफ के भीतर पाठ अंशों के स्वरूपण को कैसे अनुकूलित करूं?

 उ: आप विभिन्न गुणों को सेट करके पाठ अंशों के स्वरूपण को अनुकूलित कर सकते हैं`TextState` प्रत्येक के भीतर`TextFragment` वस्तु। वांछित दृश्य प्रभाव प्राप्त करने के लिए फ़ॉन्ट आकार, फ़ॉन्ट प्रकार, अग्रभूमि और पृष्ठभूमि रंग और रेखांकित जैसे गुणों को समायोजित किया जा सकता है।

#### प्रश्न: क्या मैं इस पद्धति का उपयोग करके अधिक जटिल टेक्स्ट रोटेशन प्रभाव बना सकता हूँ?

उत्तर: बिल्कुल. अलग-अलग रोटेशन कोणों और फ़ॉर्मेटिंग विकल्पों के साथ पुनरावृत्त रूप से कई टेक्स्ट पैराग्राफ बनाकर, आप जटिल और दृष्टि से आकर्षक टेक्स्ट रोटेशन प्रभाव प्राप्त कर सकते हैं जो आपके पीडीएफ दस्तावेज़ों की पठनीयता और सौंदर्यशास्त्र को बढ़ा सकते हैं।

#### प्रश्न: क्या टेक्स्ट रोटेशन को अन्य टेक्स्ट हेरफेर तकनीकों के साथ जोड़ना संभव है?

उत्तर: हां, आप टेक्स्ट रोटेशन को Aspose.PDF लाइब्रेरी द्वारा प्रदान की गई अन्य टेक्स्ट हेरफेर तकनीकों के साथ जोड़ सकते हैं। इसमें समृद्ध और जानकारीपूर्ण पीडीएफ दस्तावेज़ बनाने के लिए टेबल, चित्र, हाइपरलिंक और बहुत कुछ जोड़ना शामिल है।

#### प्रश्न: क्या मुझे अपने प्रोजेक्ट में Aspose.PDF लाइब्रेरी का उपयोग करने के लिए एक विशेष लाइसेंस की आवश्यकता है?

उत्तर: हाँ, आपको अपने प्रोजेक्ट में Aspose.PDF लाइब्रेरी का उपयोग करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से लाइसेंस प्राप्त कर सकते हैं, जो आपको लाइब्रेरी को प्रभावी ढंग से एकीकृत करने और उपयोग करने के लिए आवश्यक प्रमाण-पत्र प्रदान करेगा।