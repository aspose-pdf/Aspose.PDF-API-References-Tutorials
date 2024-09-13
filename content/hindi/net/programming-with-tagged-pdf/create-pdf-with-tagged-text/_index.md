---
title: टैग किए गए टेक्स्ट के साथ पीडीएफ बनाएं
linktitle: टैग किए गए टेक्स्ट के साथ पीडीएफ बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए पाठ के साथ पीडीएफ बनाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 50
url: /hi/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए टेक्स्ट के साथ एक PDF दस्तावेज़ बनाने के तरीके के बारे में चरण-दर-चरण मार्गदर्शन प्रदान करेंगे। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। Aspose.PDF की टैग की गई सामग्री संरचना सुविधाओं का उपयोग करके, आप अपने PDF दस्तावेज़ में टैग किए गए टेक्स्ट जोड़ सकते हैं।

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

## चरण 3: टैग किए गए पाठ के साथ पीडीएफ दस्तावेज़ बनाना

टैग किए गए पाठ के साथ एक पीडीएफ दस्तावेज़ बनाने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// यहां और पैराग्राफ जोड़ें

// पीडीएफ दस्तावेज़ सहेजें
document.Save(dataDir + "PDFwithTagText.pdf");
```

यह कोड एक खाली PDF दस्तावेज़ बनाता है और Aspose.PDF द्वारा प्रदान की गई विधियों का उपयोग करके टैग किए गए टेक्स्ट को जोड़ता है। आप उचित विधियों का उपयोग करके शीर्षक और पैराग्राफ जैसे अन्य टैग किए गए टेक्स्ट तत्व जोड़ सकते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए टेक्स्ट के साथ PDF बनाने के लिए नमूना स्रोत कोड 
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
// टेक्स्ट ब्लॉक-स्तरीय संरचना तत्व बनाएँ
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// पीडीएफ दस्तावेज़ सहेजें
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए टेक्स्ट के साथ PDF दस्तावेज़ कैसे बनाया जाता है। Aspose.PDF की चिह्नित सामग्री संरचना सुविधाएँ आपको बेहतर पहुँच और अर्थ के लिए अपने टेक्स्ट को संरचित और व्यवस्थित करने की अनुमति देती हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए पाठ के साथ PDF दस्तावेज़ बनाने का उद्देश्य क्या है?

उत्तर: .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए टेक्स्ट के साथ एक PDF दस्तावेज़ बनाना आपको PDF दस्तावेज़ के भीतर अपनी टेक्स्ट सामग्री को संरचित और व्यवस्थित करने की अनुमति देता है। टैग किया गया टेक्स्ट अर्थपूर्ण अर्थ जोड़ता है और उपयोगकर्ताओं के लिए पहुँच में सुधार करता है, विशेष रूप से सहायक तकनीकों का उपयोग करने वालों के लिए।

#### प्रश्न: टैग किए गए पाठ के साथ पीडीएफ दस्तावेज़ बनाने में Aspose.PDF कैसे सहायता करता है?

उत्तर: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, हेरफेर करने और परिवर्तित करने के लिए कार्यक्षमता प्रदान करती है। इस ट्यूटोरियल में, लाइब्रेरी की टैग की गई सामग्री संरचना सुविधाओं का उपयोग PDF दस्तावेज़ में संरचित और अर्थपूर्ण रूप से सार्थक पाठ जोड़ने के लिए किया जाता है।

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए पाठ के साथ एक पीडीएफ दस्तावेज़ बनाने के लिए क्या पूर्वापेक्षाएँ हैं?

उत्तर: आरंभ करने से पहले, सुनिश्चित करें कि आपके पास .NET फ्रेमवर्क के साथ Visual Studio स्थापित है और आपके प्रोजेक्ट में .NET के लिए Aspose.PDF लाइब्रेरी संदर्भित है।

#### प्रश्न: प्रदान किया गया C# कोड टैग किए गए पाठ के साथ PDF दस्तावेज़ कैसे बनाता है?

उत्तर: कोड उदाहरण दर्शाता है कि PDF दस्तावेज़ कैसे बनाएँ, विभिन्न टैग किए गए टेक्स्ट तत्वों (जैसे हेडर और पैराग्राफ़) को कैसे परिभाषित करें, और उन्हें दस्तावेज़ की सामग्री में कैसे जोड़ें। यह Aspose.PDF द्वारा प्रदान की गई टैग की गई सामग्री संरचना सुविधाओं का उपयोग करके प्राप्त किया जाता है।

#### प्रश्न: मैं टैग किए गए पाठ तत्वों, जैसे शीर्षक और पैराग्राफ़ को कैसे अनुकूलित कर सकता हूँ?

 उत्तर: आप उपयुक्त विधियों का उपयोग करके टैग किए गए पाठ तत्वों को अनुकूलित कर सकते हैं, जैसे`CreateHeaderElement` और`CreateParagraphElement` , और जैसे गुण सेट करना`ActualText` सार्थक पाठ और शब्दार्थ प्रदान करना।

#### प्रश्न: क्या मैं समान तकनीकों का उपयोग करके अन्य टैग किए गए पाठ तत्व, जैसे सूची या लिंक, जोड़ सकता हूं?

उत्तर: हाँ, आप इसी तरह की तकनीकों का उपयोग करके सूचियों, लिंक या अन्य कस्टम संरचनाओं जैसे अन्य टैग किए गए टेक्स्ट तत्व जोड़ सकते हैं। Aspose.PDF विभिन्न प्रकार की टैग की गई सामग्री बनाने के लिए विभिन्न तरीके प्रदान करता है, जिससे आप दस्तावेज़ के अर्थ को बढ़ा सकते हैं।

#### प्रश्न:`SetTitle` method contribute to the PDF document's tagged text?

 उत्तर:`SetTitle` विधि पीडीएफ दस्तावेज़ की टैग की गई सामग्री का शीर्षक सेट करती है, दस्तावेज़ के उद्देश्य या विषय का संक्षिप्त विवरण प्रदान करती है। यह जानकारी उपयोगकर्ताओं को टैग किए गए पाठ के संदर्भ को समझने में मदद करती है।

#### प्रश्न: टैग किए गए पाठ का उपयोग करने से PDF दस्तावेज़ों में पहुंच में किस प्रकार सुधार होता है?

उत्तर: टैग किया गया टेक्स्ट दस्तावेज़ में अर्थपूर्ण अर्थ जोड़ता है, जिससे यह विकलांग उपयोगकर्ताओं या सहायक तकनीकों का उपयोग करने वालों के लिए अधिक सुलभ हो जाता है। स्क्रीन रीडर और अन्य सहायक उपकरण बेहतर उपयोगकर्ता अनुभव के लिए टैग किए गए टेक्स्ट की व्याख्या और प्रस्तुति कर सकते हैं।

#### प्रश्न:`SetLanguage` method enhance the tagged text in a PDF document?

 उत्तर:`SetLanguage` विधि पीडीएफ दस्तावेज़ की टैग की गई सामग्री की भाषा विशेषता सेट करती है। यह उस भाषा को इंगित करने में मदद करता है जिसमें टैग किया गया पाठ लिखा गया है, जिससे पहुंच में सुधार होता है और उचित भाषा-विशिष्ट रेंडरिंग सक्षम होती है।

#### प्रश्न: क्या इसी प्रकार की तकनीकों का उपयोग करके टैग किए गए पाठ के साथ-साथ चित्र या मल्टीमीडिया जैसे अन्य तत्वों को जोड़ना संभव है?

उत्तर: हां, आप टैग किए गए टेक्स्ट के साथ-साथ इमेज, मल्टीमीडिया या एनोटेशन जैसे अन्य तत्व जोड़ सकते हैं। Aspose.PDF दस्तावेज़ के भीतर विभिन्न प्रकार की सामग्री को संयोजित करने के लिए कई प्रकार की सुविधाएँ प्रदान करता है।