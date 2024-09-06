---
title: संरचना तत्व बनाएँ
linktitle: संरचना तत्व बनाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस ट्यूटोरियल में, आप सीखेंगे कि टैग किए गए PDF दस्तावेज़ में संरचनात्मक तत्व बनाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें।
type: docs
weight: 60
url: /hi/net/programming-with-tagged-pdf/create-structure-elements/
---
निम्न C# स्रोत कोड संरचना तत्व बनाने के लिए .NET के लिए Aspose.PDF का उपयोग करता है। कोड कैसे काम करता है यह समझने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

```csharp
using Aspose.Pdf;
```

## चरण 2: अपने दस्तावेज़ों की निर्देशिका निर्धारित करें

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

अपने दस्तावेज़ निर्देशिका के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

## चरण 3: एक पीडीएफ दस्तावेज़ बनाएँ

```csharp
Document document = new Document();
```

हम एक नया डॉक्यूमेंट ऑब्जेक्ट बनाते हैं जो PDF डॉक्यूमेंट का प्रतिनिधित्व करता है।

## चरण 4: TaggedPdf के साथ काम करने के लिए सामग्री प्राप्त करें

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

हम पीडीएफ दस्तावेज़ की टैग की गई सामग्री को पुनः प्राप्त करते हैं। इससे हमें संरचनात्मक तत्वों में हेरफेर करने की अनुमति मिलेगी।

## चरण 5: दस्तावेज़ का शीर्षक और भाषा सेट करें

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

हम टैग किए गए पीडीएफ दस्तावेज़ का शीर्षक और भाषा सेट करते हैं। इससे दस्तावेज़ की पहुँच में सुधार होता है।

## चरण 6: समूहीकरण तत्व बनाएँ

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

हम पीडीएफ दस्तावेज़ में सामग्री को समूहीकृत करने के लिए विभिन्न संरचनात्मक तत्व बनाते हैं।

## चरण 7: पैराग्राफ़ संरचना तत्व बनाएँ

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

हम पैराग्राफ़ और शीर्षकों के लिए ब्लॉक-स्तरीय संरचनात्मक तत्व बनाते हैं। ऊपर दिया गया उदाहरण लेवल 1 हेडर के निर्माण को दर्शाता है।

## चरण 8: इनलाइन स्तर संरचना तत्व बनाएँ

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

हम पैराग्राफ या शीर्षक के अंदर दिखाई देने वाले पाठ के भागों के लिए इनलाइन स्तर संरचना तत्व बनाते हैं।

## चरण 9: कलाकृति संरचना तत्व बनाएँ

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

हम दस्तावेज़ में मौजूद चित्रों और गणितीय सूत्रों के लिए संरचनात्मक तत्वों का निर्माण करते हैं।

## चरण 10: टैग किए गए PDF दस्तावेज़ को सहेजें

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

हम टैग किए गए पीडीएफ दस्तावेज़ को निर्मित संरचना तत्वों के साथ सहेजते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके संरचना तत्व बनाने के लिए नमूना स्रोत कोड 

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
// समूहीकरण तत्व बनाएँ
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// टेक्स्ट ब्लॉक-स्तरीय संरचना तत्व बनाएँ
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// टेक्स्ट इनलाइन-स्तरीय संरचना तत्व बनाएँ
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// चित्रण संरचना तत्व बनाएँ
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// विधियाँ विकासाधीन हैं
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// टैग किए गए पीडीएफ दस्तावेज़ सहेजें
document.Save(dataDir + "StructureElements.pdf");

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि टैग किए गए PDF दस्तावेज़ में संरचना तत्व बनाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। संरचनात्मक तत्व दस्तावेज़ की पहुँच को बेहतर बनाने और सामग्री को सार्थक तरीके से व्यवस्थित करने में मदद करते हैं। अब आप इस ज्ञान का उपयोग संरचित, नेविगेट करने में आसान PDF दस्तावेज़ बनाने के लिए कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में संरचना तत्व बनाने का उद्देश्य क्या है?

उत्तर: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में संरचना तत्व बनाना दस्तावेज़ की सामग्री की पहुँच और संगठन को बढ़ाता है। संरचना तत्व एक पदानुक्रमित संरचना प्रदान करते हैं जो नेविगेशन, शब्दार्थ और सहायक तकनीकों के साथ संगतता को बेहतर बनाता है।

#### प्रश्न: प्रदान किया गया C# कोड PDF दस्तावेज़ में संरचना तत्व कैसे बनाता है?

उत्तर: कोड उदाहरण दर्शाता है कि विभिन्न प्रकार के संरचना तत्व कैसे बनाएं, जिसमें समूहीकरण तत्व (जैसे भाग, अनुभाग और divs), ब्लॉक-स्तरीय तत्व (जैसे पैराग्राफ और शीर्षक), इनलाइन-स्तरीय तत्व (स्पैन, कोट, नोट) और आर्टवर्क तत्व (जैसे आंकड़े और सूत्र) शामिल हैं। ये संरचना तत्व सामग्री को व्यवस्थित करने में मदद करते हैं।

####  प्रश्न: दस्तावेज़ का शीर्षक और भाषा सेट करना क्यों महत्वपूर्ण है?`SetTitle` and `SetLanguage` methods?

 उत्तर: दस्तावेज़ का शीर्षक और भाषा सेट करना`SetTitle` और`SetLanguage`विधियाँ दस्तावेज़ की पहुँच और अर्थविज्ञान को बेहतर बनाती हैं। शीर्षक दस्तावेज़ के उद्देश्य का संक्षिप्त विवरण प्रदान करता है, जबकि भाषा विशेषता भाषा-विशिष्ट रेंडरिंग और पहुँच को बढ़ाती है।

####  प्रश्न: तत्वों का समूहीकरण कैसे किया जाता है, जैसे`PartElement` and `SectElement`, contribute to the structure of the PDF document?

उत्तर: तत्वों को समूहीकृत करने से पीडीएफ दस्तावेज़ के भीतर एक पदानुक्रमित संरचना बनती है, जिससे आप संबंधित सामग्री को तार्किक रूप से व्यवस्थित और समूहीकृत कर सकते हैं। यह नेविगेशन को बेहतर बनाता है और उपयोगकर्ताओं के लिए एक स्पष्ट संरचना प्रदान करता है।

#### प्रश्न: ब्लॉक-स्तरीय और इनलाइन-स्तरीय संरचना तत्व क्या हैं, और वे किस प्रकार भिन्न हैं?

उत्तर: ब्लॉक-स्तरीय संरचना तत्व सामग्री के बड़े ब्लॉकों का प्रतिनिधित्व करते हैं, जैसे पैराग्राफ और शीर्षक, जबकि इनलाइन-स्तरीय तत्व पैराग्राफ या शीर्षक के भीतर पाठ के भागों का प्रतिनिधित्व करते हैं, जैसे स्पैन, उद्धरण और नोट्स। वे सामग्री के पदानुक्रम और संबंधों को परिभाषित करने में मदद करते हैं।

####  प्रश्न: कलाकृति संरचना तत्व कैसे बनाती है, जैसे`FigureElement` and `FormulaElement`, contribute to the document?

उत्तर: आर्टवर्क संरचना तत्व आपको दस्तावेज़ में चित्रण, आंकड़े और गणितीय सूत्र जोड़ने की अनुमति देते हैं। वे दृश्य और गणितीय सामग्री को शामिल करने का एक संरचित तरीका प्रदान करते हैं।

#### प्रश्न: क्या मैं अन्य प्रकार के संरचना तत्वों, जैसे सूचियाँ, तालिकाएँ या एनोटेशन बनाने के लिए समान तकनीकों का उपयोग कर सकता हूँ?

उत्तर: हां, आप अन्य प्रकार के संरचना तत्वों जैसे कि सूचियाँ, तालिकाएँ, एनोटेशन, संदर्भ, और बहुत कुछ बनाने के लिए समान तकनीकों का उपयोग कर सकते हैं। Aspose.PDF संरचना तत्व निर्माण विधियों की एक विस्तृत श्रृंखला प्रदान करता है।

####  प्रश्न: टैग किए गए पीडीएफ दस्तावेज़ को सेव करने के लिए इसका उपयोग कैसे किया जाता है?`Save` method ensure the preservation of structure elements?

 उत्तर:`Save` विधि पीडीएफ दस्तावेज़ को निर्मित संरचना तत्वों के साथ सहेजती है, यह सुनिश्चित करते हुए कि दस्तावेज़ की पदानुक्रमित और अर्थपूर्ण संरचना पहुंच और नेविगेशन के लिए संरक्षित है।

#### प्रश्न: संरचना तत्व सहायक प्रौद्योगिकियों के साथ पहुंच और संगतता के संदर्भ में पीडीएफ दस्तावेजों के लिए क्या लाभ लाते हैं?

उत्तर: संरचना तत्व दस्तावेज़ को सार्थक संरचना और अर्थ प्रदान करके पहुँच को बढ़ाते हैं। यह स्क्रीन रीडर जैसी सहायक तकनीकों को विकलांग उपयोगकर्ताओं को दस्तावेज़ की सामग्री को अधिक प्रभावी ढंग से व्याख्या करने और संप्रेषित करने की अनुमति देता है।

#### प्रश्न: मैं अपने पीडीएफ दस्तावेज़ों में विभिन्न प्रकार के संरचना तत्वों को कैसे अनुकूलित और संयोजित कर सकता हूं?

उत्तर: आप Aspose.PDF द्वारा प्रदान की गई उचित निर्माण विधियों का उपयोग करके संरचना तत्वों को संयोजित और अनुकूलित कर सकते हैं। एक अच्छी तरह से संरचित और संगठित पीडीएफ दस्तावेज़ बनाने के लिए विभिन्न तत्वों और उनके गुणों के साथ प्रयोग करें।