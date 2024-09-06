---
title: तत्व में संरचना तत्व जोड़ें
linktitle: तत्व में संरचना तत्व जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में संरचना तत्व को तत्व में जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 20
url: /hi/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में किसी तत्व में संरचना तत्व जोड़ने के बारे में चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। Aspose.PDF की चिह्नित सामग्री संरचना सुविधाओं का उपयोग करके, आप अपने PDF दस्तावेज़ में एक पदानुक्रमित संरचना बना सकते हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. .NET फ्रेमवर्क के साथ स्थापित विजुअल स्टूडियो.
2. .NET के लिए Aspose.PDF लाइब्रेरी.

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, Visual Studio में एक नया प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। आप Aspose की आधिकारिक वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं और इसे अपनी मशीन पर इंस्टॉल कर सकते हैं।

## चरण 2: आवश्यक नामस्थान आयात करें

अपनी C# कोड फ़ाइल में, Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करें:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## चरण 3: पीडीएफ दस्तावेज़ बनाना और संरचित तत्वों को परिभाषित करना

पीडीएफ दस्तावेज़ बनाने और संरचित तत्वों को परिभाषित करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

यह कोड एक खाली PDF दस्तावेज़ बनाता है और पैराग्राफ़ और स्पैन जैसे संरचित तत्व जोड़ता है। प्रत्येक संरचना तत्व Aspose.PDF द्वारा प्रदान की गई विधियों का उपयोग करके बनाया जाता है।

## चरण 4: पीडीएफ दस्तावेज़ को सहेजना

पीडीएफ दस्तावेज़ को सहेजने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
document. Save(outFile);
```

यह कोड संरचित तत्वों के साथ पीडीएफ दस्तावेज़ को निर्दिष्ट फ़ाइल में सहेजता है।

### .NET के लिए Aspose.PDF का उपयोग करके तत्व में संरचना तत्व जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// दस्तावेज़ बनाना और टैग की गई पीडीएफ सामग्री प्राप्त करना
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// दस्तावेज़ के लिए शीर्षक और प्रकृति भाषा सेट करना
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// रूट संरचना तत्व (दस्तावेज़ संरचना तत्व) प्राप्त करना
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// टैग किए गए पीडीएफ दस्तावेज़ सहेजें
document.Save(outFile);
// PDF/UA अनुपालन की जाँच करना
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में किसी तत्व में संरचना तत्व कैसे जोड़ा जाता है। Aspose.PDF की चिह्नित सामग्री संरचना सुविधाओं का उपयोग करके, आप अपने PDF दस्तावेज़ में एक पदानुक्रमित संरचना बना सकते हैं, जिससे सामग्री को प्रबंधित करना और नेविगेट करना आसान हो जाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में किसी तत्व में संरचना तत्व जोड़ने का उद्देश्य क्या है?

उत्तर: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में किसी तत्व में संरचना तत्व जोड़ने से आप दस्तावेज़ की सामग्री के भीतर एक पदानुक्रमित संरचना बना सकते हैं। यह पदानुक्रमित संरचना सामग्री के संगठन और नेविगेशन को बढ़ाती है, जिससे विशिष्ट तत्वों को प्रबंधित करना और उन तक पहुँचना आसान हो जाता है।

#### प्रश्न: Aspose.PDF लाइब्रेरी PDF दस्तावेज़ में संरचना तत्वों को जोड़ने में कैसे सहायता करती है?

उत्तर: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, हेरफेर करने और परिवर्तित करने की क्षमता प्रदान करती है। इस ट्यूटोरियल में, लाइब्रेरी की चिह्नित सामग्री संरचना सुविधाओं का उपयोग PDF दस्तावेज़ की सामग्री में संरचना तत्वों को बनाने और जोड़ने के लिए किया जाता है।

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में संरचना तत्व जोड़ने के लिए क्या पूर्वापेक्षाएँ हैं?

उत्तर: आरंभ करने से पहले, सुनिश्चित करें कि आपके पास .NET फ्रेमवर्क के साथ Visual Studio स्थापित है और आपके प्रोजेक्ट में .NET के लिए Aspose.PDF लाइब्रेरी संदर्भित है।

#### प्रश्न: प्रदान किया गया C# कोड PDF दस्तावेज़ की सामग्री में संरचना तत्वों को कैसे बनाता और जोड़ता है?

उत्तर: कोड दर्शाता है कि PDF दस्तावेज़ कैसे बनाएँ, मूल संरचना तत्व को कैसे परिभाषित करें, तथा पैराग्राफ़ और स्पैन जैसे विभिन्न संरचित तत्वों को इसमें कैसे जोड़ें। प्रत्येक संरचित तत्व Aspose.PDF द्वारा प्रदान की गई विधियों का उपयोग करके बनाया जाता है, जिससे आप एक पदानुक्रमित संरचना बना सकते हैं।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में जोड़े जाने वाले संरचना तत्वों के प्रकार को अनुकूलित कर सकता हूँ?

उत्तर: हाँ, आप Aspose.PDF लाइब्रेरी द्वारा प्रदान की गई विभिन्न विधियों का पता लगाकर संरचना तत्वों के प्रकारों को अनुकूलित कर सकते हैं। कोड पैराग्राफ़ और स्पैन को उदाहरण के रूप में प्रदर्शित करता है, लेकिन आप आवश्यकतानुसार अन्य प्रकार के संरचित तत्व बना और जोड़ सकते हैं।

#### प्रश्न: मैं जोड़े गए संरचना तत्वों के बीच पदानुक्रमिक संबंध कैसे परिभाषित करूं?

 उत्तर: संरचना तत्वों के बीच पदानुक्रमिक संबंध उस क्रम से परिभाषित होता है जिसमें आप उन्हें उनके मूल तत्वों में जोड़ते हैं। कोड में, पैरेंट-चाइल्ड संबंध का उपयोग करके स्थापित किया जाता है`AppendChild` तरीका।

#### प्रश्न: पीडीएफ दस्तावेज़ में पदानुक्रमित संरचना बनाने के क्या लाभ हैं?

उत्तर: PDF दस्तावेज़ में पदानुक्रमित संरचना बनाने से इसकी पहुँच, नेविगेशन और संगठन में सुधार होता है। यह सहायक तकनीकों को दस्तावेज़ की सामग्री को बेहतर ढंग से समझने और संप्रेषित करने की अनुमति देता है, जिससे यह विकलांग व्यक्तियों के लिए अधिक उपयोगकर्ता-अनुकूल बन जाता है।

#### प्रश्न: संरचना तत्वों को जोड़ने के बाद मैं PDF/UA अनुपालन को कैसे सत्यापित कर सकता हूं?

 उत्तर: ट्यूटोरियल में दिया गया कोड यह दर्शाता है कि PDF/UA अनुपालन को सत्यापित करने के लिए इसका उपयोग कैसे किया जाता है।`Validate` विधि। PDF/UA मानक के विरुद्ध दस्तावेज़ को मान्य करके, आप यह सुनिश्चित कर सकते हैं कि जोड़े गए संरचना तत्व पहुँच-योग्यता दिशानिर्देशों के अनुरूप हैं।

#### प्रश्न: क्या मैं किसी मौजूदा PDF दस्तावेज़ में संरचना तत्व जोड़ने के लिए इस दृष्टिकोण का उपयोग कर सकता हूँ?

उत्तर: हां, आप मौजूदा PDF दस्तावेज़ में संरचना तत्व जोड़ने के लिए दिए गए दृष्टिकोण को संशोधित कर सकते हैं। नया दस्तावेज़ बनाने के बजाय, आप Aspose.PDF का उपयोग करके मौजूदा दस्तावेज़ को लोड करेंगे और फिर संरचना तत्वों को जोड़ने के लिए समान चरणों का पालन करेंगे।