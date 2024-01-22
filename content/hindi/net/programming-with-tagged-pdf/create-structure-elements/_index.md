---
title: संरचना तत्व बनाएं
linktitle: संरचना तत्व बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस ट्यूटोरियल में, आप सीखेंगे कि टैग किए गए पीडीएफ दस्तावेज़ में संरचनात्मक तत्व बनाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें।
type: docs
weight: 60
url: /hi/net/programming-with-tagged-pdf/create-structure-elements/
---
निम्नलिखित C# स्रोत कोड संरचना तत्व बनाने के लिए .NET के लिए Aspose.PDF का उपयोग करता है। कोड कैसे काम करता है यह समझने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: आवश्यक पुस्तकालय आयात करें

```csharp
using Aspose.Pdf;
```

## चरण 2: अपने दस्तावेज़ों की निर्देशिका परिभाषित करें

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

अपनी दस्तावेज़ निर्देशिका के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

## चरण 3: एक पीडीएफ दस्तावेज़ बनाएं

```csharp
Document document = new Document();
```

हम एक नया दस्तावेज़ ऑब्जेक्ट बनाते हैं जो पीडीएफ दस्तावेज़ का प्रतिनिधित्व करता है।

## चरण 4: TaggedPdf के साथ काम करने के लिए सामग्री प्राप्त करें

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

हम पीडीएफ दस्तावेज़ की टैग की गई सामग्री पुनः प्राप्त करते हैं। यह हमें संरचनात्मक तत्वों में हेरफेर करने की अनुमति देगा।

## चरण 5: दस्तावेज़ का शीर्षक और भाषा सेट करें

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

हम टैग किए गए पीडीएफ दस्तावेज़ का शीर्षक और भाषा निर्धारित करते हैं। इससे दस्तावेज़ की पहुंच में सुधार होता है.

## चरण 6: समूहीकरण तत्व बनाएं

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

## चरण 7: पैराग्राफ संरचना तत्व बनाएं

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

हम पैराग्राफ और शीर्षकों के लिए ब्लॉक-स्तरीय संरचनात्मक तत्व बनाते हैं। उपरोक्त उदाहरण लेवल 1 हेडर के निर्माण को दर्शाता है।

## चरण 8: इनलाइन स्तर संरचना तत्व बनाएं

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

हम पाठ के उन हिस्सों के लिए इनलाइन स्तर संरचना तत्व बनाते हैं जो पैराग्राफ या शीर्षक के अंदर दिखाई देते हैं।

## चरण 9: कलाकृति संरचना तत्व बनाएं

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

हम दस्तावेज़ में मौजूद चित्रों और गणितीय सूत्रों के लिए संरचनात्मक तत्व बनाते हैं।

## चरण 10: टैग किए गए पीडीएफ दस्तावेज़ को सहेजें

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
// डॉक्युमनेट के लिए शीर्षक और भाषा सेट करें
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// समूहीकरण तत्व बनाएं
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
// टेक्स्ट ब्लॉक-स्तरीय संरचना तत्व बनाएं
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// टेक्स्ट इनलाइन-स्तरीय संरचना तत्व बनाएं
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// चित्रण संरचना तत्व बनाएं
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// तरीके विकासाधीन हैं
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
// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "StructureElements.pdf");

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि टैग किए गए पीडीएफ दस्तावेज़ में संरचना तत्व बनाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। संरचनात्मक तत्व दस्तावेज़ की पहुंच को बेहतर बनाने और सामग्री को सार्थक तरीके से व्यवस्थित करने में मदद करते हैं। अब आप इस ज्ञान का उपयोग संरचित, नेविगेट करने में आसान पीडीएफ दस्तावेज़ बनाने के लिए कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में संरचना तत्व बनाने का उद्देश्य क्या है?

उ: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में संरचना तत्व बनाने से दस्तावेज़ की सामग्री की पहुंच और संगठन में वृद्धि होती है। संरचना तत्व एक पदानुक्रमित संरचना प्रदान करते हैं जो नेविगेशन, शब्दार्थ और सहायक प्रौद्योगिकियों के साथ संगतता में सुधार करता है।

#### प्रश्न: प्रदान किया गया C# कोड पीडीएफ दस्तावेज़ में संरचना तत्व कैसे बनाता है?

ए: कोड उदाहरण दर्शाता है कि विभिन्न प्रकार के संरचना तत्वों को कैसे बनाया जाए, जिसमें समूहीकरण तत्व (जैसे कि भाग, अनुभाग और divs), ब्लॉक-स्तरीय तत्व (जैसे पैराग्राफ और शीर्षक), इनलाइन-स्तरीय तत्व (स्पैन, उद्धरण, नोट) शामिल हैं। ), और कलाकृति तत्व (जैसे आंकड़े और सूत्र)। ये संरचना तत्व सामग्री को व्यवस्थित करने में मदद करते हैं।

####  प्रश्न: दस्तावेज़ का शीर्षक और भाषा का उपयोग करके सेट करना क्यों महत्वपूर्ण है?`SetTitle` and `SetLanguage` methods?

 A: का उपयोग करके दस्तावेज़ का शीर्षक और भाषा सेट करना`SetTitle` और`SetLanguage`विधियाँ दस्तावेज़ पहुंच और शब्दार्थ में सुधार करती हैं। शीर्षक दस्तावेज़ के उद्देश्य का संक्षिप्त विवरण प्रदान करता है, जबकि भाषा विशेषता भाषा-विशिष्ट प्रतिपादन और पहुंच को बढ़ाती है।

####  प्रश्न: तत्वों का समूहन कैसे किया जाता है, जैसे`PartElement` and `SectElement`, contribute to the structure of the PDF document?

उ: समूहीकरण तत्व पीडीएफ दस्तावेज़ के भीतर एक पदानुक्रमित संरचना बनाते हैं, जिससे आप संबंधित सामग्री को तार्किक रूप से व्यवस्थित और समूहित कर सकते हैं। यह नेविगेशन को बढ़ाता है और उपयोगकर्ताओं के लिए एक स्पष्ट संरचना प्रदान करता है।

#### प्रश्न: ब्लॉक-स्तरीय और इनलाइन-स्तरीय संरचना तत्व क्या हैं, और वे कैसे भिन्न हैं?

ए: ब्लॉक-स्तरीय संरचना तत्व सामग्री के बड़े ब्लॉकों का प्रतिनिधित्व करते हैं, जैसे पैराग्राफ और शीर्षक, जबकि इनलाइन-स्तरीय तत्व पैराग्राफ या शीर्षक के भीतर पाठ के कुछ हिस्सों, जैसे स्पैन, उद्धरण और नोट्स का प्रतिनिधित्व करते हैं। वे सामग्री के पदानुक्रम और संबंधों को परिभाषित करने में मदद करते हैं।

####  प्रश्न: कलाकृति की संरचना के तत्व कैसे होते हैं?`FigureElement` and `FormulaElement`, contribute to the document?

उ: कलाकृति संरचना तत्व आपको दस्तावेज़ में चित्र, आंकड़े और गणितीय सूत्र जोड़ने की अनुमति देते हैं। वे दृश्य और गणितीय सामग्री को शामिल करने का एक संरचित तरीका प्रदान करते हैं।

#### प्रश्न: क्या मैं अन्य प्रकार के संरचना तत्व, जैसे सूचियाँ, तालिकाएँ, या एनोटेशन बनाने के लिए समान तकनीकों का उपयोग कर सकता हूँ?

उत्तर: हाँ, आप अन्य प्रकार के संरचना तत्व जैसे सूचियाँ, तालिकाएँ, एनोटेशन, संदर्भ और बहुत कुछ बनाने के लिए समान तकनीकों का उपयोग कर सकते हैं। Aspose.PDF संरचना तत्व निर्माण विधियों की एक विस्तृत श्रृंखला प्रदान करता है।

####  प्रश्न: टैग किए गए पीडीएफ दस्तावेज़ को कैसे सहेजा जाता है?`Save` method ensure the preservation of structure elements?

 ए: द`Save` विधि निर्मित संरचना तत्वों के साथ पीडीएफ दस्तावेज़ को सहेजती है, यह सुनिश्चित करती है कि दस्तावेज़ की पदानुक्रमित और अर्थपूर्ण संरचना पहुंच और नेविगेशन के लिए संरक्षित है।

#### प्रश्न: सहायक प्रौद्योगिकियों के साथ पहुंच और अनुकूलता के संदर्भ में संरचना तत्व पीडीएफ दस्तावेज़ों में क्या लाभ लाते हैं?

उत्तर: संरचना तत्व दस्तावेज़ को एक सार्थक संरचना और शब्दार्थ प्रदान करके पहुंच बढ़ाते हैं। यह स्क्रीन रीडर जैसी सहायक तकनीकों को दस्तावेज़ की सामग्री की व्याख्या करने और विकलांग उपयोगकर्ताओं तक अधिक प्रभावी ढंग से पहुंचाने की अनुमति देता है।

#### प्रश्न: मैं अपने पीडीएफ दस्तावेजों में विभिन्न प्रकार के संरचना तत्वों को और कैसे अनुकूलित और संयोजित कर सकता हूं?

उ: आप Aspose.PDF द्वारा प्रदान की गई उपयुक्त निर्माण विधियों का उपयोग करके संरचना तत्वों को संयोजित और अनुकूलित कर सकते हैं। एक अच्छी तरह से संरचित और व्यवस्थित पीडीएफ दस्तावेज़ बनाने के लिए विभिन्न तत्वों और उनके गुणों के साथ प्रयोग करें।