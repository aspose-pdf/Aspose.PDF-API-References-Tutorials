---
title: नोट संरचना तत्व बनाएं
linktitle: नोट संरचना तत्व बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में संरचित नोट आइटम बनाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 30
url: /hi/net/programming-with-tagged-pdf/create-note-structure-element/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में नोट संरचना तत्व बनाने के तरीके के बारे में चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको पीडीएफ दस्तावेजों को प्रोग्रामेटिक रूप से बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। Aspose.PDF की चिह्नित सामग्री संरचना सुविधाओं का उपयोग करके, आप अपने पीडीएफ दस्तावेज़ में संरचित नोट्स जोड़ सकते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. विजुअल स्टूडियो .NET फ्रेमवर्क के साथ स्थापित किया गया है।
2. .NET के लिए Aspose.PDF लाइब्रेरी।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, विज़ुअल स्टूडियो में एक नया प्रोजेक्ट बनाएं और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। आप Aspose की आधिकारिक वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं और इसे अपनी मशीन पर इंस्टॉल कर सकते हैं।

## चरण 2: आवश्यक नामस्थान आयात करें

अपनी C# कोड फ़ाइल में, Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## चरण 3: पीडीएफ दस्तावेज़ और नोट संरचित तत्व बनाना

पीडीएफ दस्तावेज़ बनाने और नोट संरचित तत्वों को जोड़ने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

यह कोड एक खाली पीडीएफ दस्तावेज़ बनाता है और एक पैराग्राफ में संरचित नोट तत्व जोड़ता है। प्रत्येक नोट Aspose.PDF द्वारा प्रदान की गई विधियों का उपयोग करके बनाया गया है।

## चरण 4: पीडीएफ दस्तावेज़ को सहेजना

पीडीएफ दस्तावेज़ को सहेजने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
document. Save(outFile);
```

यह कोड पीडीएफ दस्तावेज़ को नोट संरचित तत्वों के साथ एक निर्दिष्ट फ़ाइल में सहेजता है।

### .NET के लिए Aspose.PDF का उपयोग करके नोट संरचना तत्व बनाने के लिए नमूना स्रोत कोड 

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// पीडीएफ दस्तावेज़ बनाएं
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// अनुच्छेद तत्व जोड़ें
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// नोट एलिमेंट जोड़ें
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// नोट एलिमेंट जोड़ें
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// नोट एलिमेंट जोड़ें
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// अपवाद अवश्य फेंकें - Aspose.Pdf.Tagged.TaggedException : ID='note_002' वाला संरचना तत्व पहले से मौजूद है
//Note3.SetId('note_002');
// यदि नोट संरचना तत्व के लिए ClearId() का उपयोग किया जाता है तो परिणामी दस्तावेज़ पीडीएफ/यूए का अनुपालन नहीं करता है
//नोट3.ClearId();
// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(outFile);
// पीडीएफ/यूए अनुपालन की जाँच करना
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में नोट संरचना तत्व कैसे बनाएं। संरचित नोट तत्व आपको अपने पीडीएफ दस्तावेज़ में अतिरिक्त, संरचित जानकारी जोड़ने की अनुमति देते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में नोट संरचना तत्व बनाने का उद्देश्य क्या है?

उ: .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में नोट संरचना तत्व बनाने से आप दस्तावेज़ की सामग्री में संरचित नोट्स जोड़ सकते हैं। ये नोट्स सामग्री के विशिष्ट भागों के लिए अतिरिक्त संदर्भ, स्पष्टीकरण या संदर्भ प्रदान कर सकते हैं।

#### प्रश्न: Aspose.PDF लाइब्रेरी पीडीएफ दस्तावेज़ में नोट संरचना तत्व बनाने में कैसे सहायता करती है?

उत्तर: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो पीडीएफ दस्तावेजों को प्रोग्रामेटिक रूप से बनाने, हेरफेर करने और परिवर्तित करने के लिए कार्यक्षमता प्रदान करती है। इस ट्यूटोरियल में, लाइब्रेरी की चिह्नित सामग्री संरचना सुविधाओं का उपयोग पीडीएफ दस्तावेज़ की सामग्री के भीतर संरचित नोट तत्व बनाने के लिए किया जाता है।

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में नोट संरचना तत्व बनाने के लिए पूर्वापेक्षाएँ क्या हैं?

उ: शुरू करने से पहले, सुनिश्चित करें कि आपके पास .NET फ्रेमवर्क के साथ विजुअल स्टूडियो स्थापित है और आपके प्रोजेक्ट में .NET के लिए Aspose.PDF लाइब्रेरी का संदर्भ दिया गया है।

#### प्रश्न: प्रदान किया गया C# कोड पीडीएफ दस्तावेज़ की सामग्री में नोट संरचना तत्व कैसे बनाता है?

उ: कोड दर्शाता है कि एक पीडीएफ दस्तावेज़ कैसे बनाया जाए, नोट संरचित तत्वों को कैसे परिभाषित किया जाए और उन्हें एक पैराग्राफ में कैसे जोड़ा जाए। प्रत्येक नोट Aspose.PDF द्वारा प्रदान की गई विधियों का उपयोग करके बनाया गया है, जो आपको सामग्री में संरचित नोट्स को शामिल करने की अनुमति देता है।

#### प्रश्न: क्या मैं अपने द्वारा बनाए गए नोट संरचना तत्वों की सामग्री और गुणों को अनुकूलित कर सकता हूं?

उत्तर: हां, आप Aspose.PDF लाइब्रेरी द्वारा प्रदान की गई विधियों और गुणों का उपयोग करके नोट संरचना तत्वों की सामग्री और गुणों को अनुकूलित कर सकते हैं। कोड दिखाता है कि नोट तत्वों का टेक्स्ट और आईडी कैसे सेट करें, लेकिन आप आवश्यकतानुसार उन्हें और अनुकूलित कर सकते हैं।

#### प्रश्न: नोट संरचना तत्वों और दस्तावेज़ की सामग्री के बीच पदानुक्रमित संबंध कैसे स्थापित किया जाता है?

 उत्तर: नोट संरचना तत्वों को पैराग्राफ जैसे अन्य संरचित तत्वों के बच्चों के रूप में जोड़कर पदानुक्रमित संबंध स्थापित किया जाता है। कोड में, नोट तत्वों को पैराग्राफ तत्व का उपयोग करके जोड़ा जाता है`AppendChild` तरीका।

#### प्रश्न: क्या मैं संरचना तत्वों को नोट करने के लिए अद्वितीय आईडी निर्दिष्ट कर सकता हूं?

उ: हाँ, आप इसका उपयोग करके संरचना तत्वों को नोट करने के लिए अद्वितीय आईडी निर्दिष्ट कर सकते हैं`SetId` तरीका। कोड दर्शाता है कि नोट तत्वों की आईडी को अद्वितीय मानों पर कैसे सेट किया जाए।

#### प्रश्न: यदि मैं किसी नोट संरचना तत्व को डुप्लिकेट आईडी निर्दिष्ट करने का प्रयास करूं तो क्या होगा?

उ: किसी नोट संरचना तत्व को डुप्लिकेट आईडी निर्दिष्ट करने का प्रयास करने पर एक अपवाद उत्पन्न होगा। ट्यूटोरियल में दिए गए कोड में इस परिदृश्य को दर्शाने वाली एक टिप्पणी शामिल है।

#### प्रश्न: नोट संरचना तत्व बनाते समय मैं पीडीएफ/यूए अनुपालन कैसे सुनिश्चित कर सकता हूं?

 उ: ट्यूटोरियल में प्रदान किया गया कोड दर्शाता है कि इसका उपयोग करके पीडीएफ/यूए अनुपालन को कैसे मान्य किया जाए`Validate` तरीका। दस्तावेज़ को पीडीएफ/यूए मानक के विरुद्ध सत्यापित करके, आप यह सुनिश्चित कर सकते हैं कि जोड़े गए नोट संरचना तत्व पहुंच संबंधी दिशानिर्देशों का पालन करते हैं।

#### प्रश्न: क्या मैं मौजूदा पीडीएफ दस्तावेज़ में नोट संरचना तत्वों को जोड़ने के लिए इस दृष्टिकोण का उपयोग कर सकता हूं?

उ: हां, आप मौजूदा पीडीएफ दस्तावेज़ में नोट संरचना तत्वों को जोड़ने के लिए दिए गए दृष्टिकोण को संशोधित कर सकते हैं। एक नया दस्तावेज़ बनाने के बजाय, आप Aspose.PDF का उपयोग करके मौजूदा दस्तावेज़ को लोड करेंगे और फिर नोट तत्वों को जोड़ने के लिए समान चरणों का पालन करेंगे।
