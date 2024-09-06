---
title: इनलाइन संरचना तत्व
linktitle: इनलाइन संरचना तत्व
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ ऑनलाइन संरचनात्मक तत्वों का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका। अपने PDF को शीर्षकों और पैराग्राफ़ के साथ व्यवस्थित करें।
type: docs
weight: 110
url: /hi/net/programming-with-tagged-pdf/inline-structure-elements/
---
इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF के साथ इनलाइन संरचना तत्वों का उपयोग कैसे करें। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ों में हेरफेर करने देती है। इनलाइन संरचना तत्व आपको विभिन्न स्तरों और पैराग्राफ़ के शीर्षकों का उपयोग करके अपने PDF दस्तावेज़ में एक पदानुक्रमित संरचना बनाने की अनुमति देते हैं।

आइए कोड में गोता लगाएँ और सीखें कि .NET के लिए Aspose.PDF के साथ इनलाइन संरचना तत्वों का उपयोग कैसे करें।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. .NET के लिए Aspose.PDF लाइब्रेरी स्थापित।
2. C# प्रोग्रामिंग भाषा का मूलभूत ज्ञान।

## चरण 1: वातावरण की स्थापना

आरंभ करने के लिए, अपना C# डेवलपमेंट एनवायरनमेंट खोलें और एक नया प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.PDF लाइब्रेरी का संदर्भ जोड़ा है।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाना

 पहला कदम का उपयोग कर एक नया पीडीएफ दस्तावेज़ बनाना है`Document` कक्षा।

```csharp
// पीडीएफ दस्तावेज़ बनाएं
Document document = new Document();
```

## चरण 3: टैग की गई सामग्री के साथ काम करें

फिर हमें कार्य करने के लिए दस्तावेज़ की टैग की गई सामग्री मिलती है।

```csharp
// दस्तावेज़ की टैग की गई सामग्री प्राप्त करें
ITaggedContent taggedContent = document.TaggedContent;
```

## चरण 4: दस्तावेज़ का शीर्षक और भाषा सेट करें

अब हम दस्तावेज़ का शीर्षक और भाषा निर्धारित कर सकते हैं।

```csharp
// दस्तावेज़ का शीर्षक और भाषा निर्धारित करें
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## चरण 5: संरचनात्मक तत्वों को ऑनलाइन जोड़ें

अब हम अपने दस्तावेज़ में विभिन्न स्तरों और पैराग्राफों के शीर्षकों जैसे इनलाइन संरचना तत्वों को जोड़ने जा रहे हैं।

```csharp
// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// विभिन्न स्तरों के हेडर जोड़ें
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// प्रत्येक हेडर में सामग्री जोड़ें
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// एक पैराग्राफ़ जोड़ें
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// पैराग्राफ़ में सामग्री जोड़ें
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

यहां हम इनलाइन संरचना तत्व बनाते हैं, जैसे विभिन्न स्तरों के शीर्षक और पैराग्राफ, और उनमें सामग्री जोड़ते हैं।

## चरण 6: टैग किए गए PDF दस्तावेज़ को सहेजें

अंत में, हम टैग किए गए पीडीएफ दस्तावेज़ को सेव कर लेते हैं।

```csharp
// टैग किए गए PDF दस्तावेज़ को सहेजें
document.Save(dataDir + "InlineStructureElements.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके इनलाइन संरचना तत्वों के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// पीडीएफ दस्तावेज़ बनाएं
Document document = new Document();

// TaggedPdf के साथ काम के लिए सामग्री प्राप्त करें
ITaggedContent taggedContent = document.TaggedContent;

// Documnet के लिए शीर्षक और भाषा सेट करें
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// टैग किए गए पीडीएफ दस्तावेज़ सहेजें
document.Save(dataDir + "InlineStructureElements.pdf");

```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF के साथ इनलाइन संरचना तत्वों का उपयोग करना सीख लिया है। अब आप विभिन्न स्तरों और पैराग्राफ़ के शीर्षकों का उपयोग करके अपने PDF दस्तावेज़ में एक पदानुक्रमित संरचना बना सकते हैं। Aspose.PDF की पूरी क्षमता का पता लगाने के लिए इसकी अधिक विशेषताओं का अन्वेषण करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में इनलाइन संरचना तत्व क्या हैं, और वे पदानुक्रमित संरचना बनाने में कैसे योगदान करते हैं?

उत्तर: पीडीएफ दस्तावेज़ में इनलाइन संरचना तत्व, जैसे कि विभिन्न स्तरों और पैराग्राफ के शीर्षक, एक पदानुक्रमित संरचना बनाने के लिए उपयोग किए जाते हैं जो सामग्री को संरचित तरीके से व्यवस्थित और प्रस्तुत करता है। ये तत्व आपको दस्तावेज़ के भीतर एक स्पष्ट पदानुक्रम और सूचना का प्रवाह स्थापित करने की अनुमति देते हैं।

#### प्रश्न: इनलाइन संरचना तत्व पीडीएफ दस्तावेज़ की पठनीयता और संगठन को कैसे बढ़ा सकते हैं?

उत्तर: इनलाइन संरचना तत्व, विशेष रूप से शीर्षक और पैराग्राफ, तार्किक संरचना प्रदान करके पीडीएफ दस्तावेज़ की पठनीयता और संगठन को बेहतर बनाने में मदद करते हैं। शीर्षक महत्व के विभिन्न स्तरों को इंगित करते हैं और पाठकों को सामग्री को नेविगेट करने में मदद करते हैं, जबकि पैराग्राफ संबंधित जानकारी को एक साथ समूहित करते हैं।

#### प्रश्न: .NET के लिए Aspose.PDF इनलाइन संरचना तत्वों के उपयोग को कैसे सुविधाजनक बनाता है?

उत्तर: .NET के लिए Aspose.PDF इनलाइन संरचना तत्वों, जैसे शीर्षकों और पैराग्राफ़ों को बनाने और उनमें हेरफेर करने के लिए क्लास और विधियाँ प्रदान करता है। इन तत्वों को अनुकूलित किया जा सकता है, पदानुक्रमिक रूप से व्यवस्थित किया जा सकता है, और दस्तावेज़ की दृश्य प्रस्तुति और पहुँच को बेहतर बनाने के लिए सामग्री से समृद्ध किया जा सकता है।

####  प्रश्न: इसका उद्देश्य क्या है?`taggedContent` object in relation to inline structure elements?

 उत्तर:`taggedContent` वस्तु, से प्राप्त`TaggedContent` एक की संपत्ति`Document`, आपको इनलाइन संरचना तत्वों सहित संरचित तत्वों के साथ काम करने की अनुमति देता है। यह आपको दस्तावेज़ के भीतर शीर्षकों और पैराग्राफ़ों को बनाने, अनुकूलित करने और व्यवस्थित करने में सक्षम बनाता है।

#### प्रश्न: इनलाइन संरचना तत्व स्पष्ट दस्तावेज़ पदानुक्रम बनाने में कैसे सहायता करते हैं?

उत्तर: इनलाइन संरचना तत्व, जैसे कि अलग-अलग स्तरों के शीर्षक, दस्तावेज़ में एक स्पष्ट और अच्छी तरह से परिभाषित पदानुक्रम स्थापित करने में योगदान करते हैं। पाठक मुख्य विषयों, उप-विषयों और संबंधित सामग्री को जल्दी से पहचान सकते हैं, जिससे दस्तावेज़ को नेविगेट करना और समझना आसान हो जाता है।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके इनलाइन संरचना तत्वों की उपस्थिति और स्वरूपण को अनुकूलित कर सकता हूं?

उत्तर: हां, आप इनलाइन संरचना तत्वों की उपस्थिति और स्वरूपण को अनुकूलित कर सकते हैं। आप शीर्षकों और पैराग्राफ़ के लिए वांछित दृश्य प्रस्तुति प्राप्त करने के लिए फ़ॉन्ट शैली, आकार, रंग, संरेखण, इंडेंटेशन और रिक्ति जैसे गुण सेट कर सकते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.PDF में इनलाइन संरचना तत्वों का उपयोग करके PDF दस्तावेज़ में विभिन्न स्तरों के शीर्षक कैसे बनाऊं और जोड़ूं?

 उत्तर: आप इसका उपयोग करके विभिन्न स्तरों के शीर्षक बना सकते हैं।`CreateHeaderElement` विधि और फिर उन्हें मूल संरचना तत्व में जोड़ें। इसके बाद, आप प्रत्येक शीर्षक तत्व में सामग्री जोड़ सकते हैं`CreateSpanElement` पाठ के विस्तार बनाने की विधि.

#### प्रश्न: क्या मैं PDF दस्तावेज़ में सूचियाँ, बुलेट पॉइंट या अन्य प्रकार की सामग्री संगठन बनाने के लिए इनलाइन संरचना तत्वों का उपयोग कर सकता हूँ?

उत्तर: जबकि इनलाइन संरचना तत्वों का उपयोग मुख्य रूप से शीर्षकों और पैराग्राफों के लिए किया जाता है, आप उन्हें .NET के लिए Aspose.PDF द्वारा प्रस्तुत अन्य सुविधाओं के साथ संयोजन में उपयोग कर सकते हैं ताकि एक व्यापक दस्तावेज़ संरचना के लिए सूचियाँ, बुलेट पॉइंट, तालिकाएँ और अन्य प्रकार के सामग्री संगठन का निर्माण किया जा सके।

#### प्रश्न: इनलाइन संरचना तत्व दस्तावेज़ की पहुंच में किस प्रकार योगदान देते हैं?

उत्तर: इनलाइन संरचना तत्व दस्तावेज़ की पहुँच बढ़ाने में महत्वपूर्ण भूमिका निभाते हैं। उचित रूप से संरचित शीर्षक और पैराग्राफ एक स्पष्ट दस्तावेज़ पदानुक्रम प्रदान करते हैं जो स्क्रीन रीडर और अन्य सहायक तकनीकों को विकलांग उपयोगकर्ताओं को सामग्री की सटीक व्याख्या करने और संप्रेषित करने में सहायता करता है।

#### प्रश्न: क्या मैं इनलाइन संरचना तत्वों के अधिक उन्नत उपयोगों का पता लगा सकता हूं, जैसे कि इंटरैक्टिव तत्व बनाना या मल्टीमीडिया एम्बेड करना?

उत्तर: बिल्कुल! जबकि यह ट्यूटोरियल हेडिंग और पैराग्राफ़ बनाने पर केंद्रित है, Aspose.PDF for .NET इंटरैक्टिव तत्व बनाने, मल्टीमीडिया एम्बेड करने, हाइपरलिंक जोड़ने और बहुत कुछ करने के लिए उन्नत सुविधाएँ प्रदान करता है। इन उन्नत क्षमताओं को जानने के लिए लाइब्रेरी के दस्तावेज़ और उदाहरण देखें।