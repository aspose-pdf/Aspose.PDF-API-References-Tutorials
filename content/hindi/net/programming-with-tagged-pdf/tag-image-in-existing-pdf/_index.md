---
title: मौजूदा पीडीएफ में छवि टैग करें
linktitle: मौजूदा पीडीएफ में छवि टैग करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि .NET के लिए Aspose.PDF के साथ मौजूदा PDF में किसी छवि को कैसे चिह्नित किया जाए। छवियों में टैग जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 210
url: /hi/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
इस विस्तृत ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ में एक छवि को चिह्नित करने के लिए चरण दर चरण दिए गए C# स्रोत कोड के बारे में बताएंगे। पीडीएफ में किसी छवि में टैग कैसे जोड़ें, यह समझने के लिए नीचे दिए गए निर्देशों का पालन करें।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपने विकास परिवेश को कॉन्फ़िगर कर लिया है। इसमें Aspose.PDF लाइब्रेरी स्थापित करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

## चरण 2: मौजूदा पीडीएफ दस्तावेज़ खोलें

इस चरण में, हम Aspose.PDF का उपयोग करके एक मौजूदा पीडीएफ दस्तावेज़ खोलेंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// इनपुट और आउटपुट फ़ाइल पथ
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// दस्तावेज़ खोलें
Document document = new Document(inFile);
```

हमने Aspose.PDF का उपयोग करके मौजूदा PDF दस्तावेज़ खोला।

## चरण 3: टैग की गई सामग्री और मूल संरचना तत्व प्राप्त करें

अब हमें पीडीएफ दस्तावेज़ की टैग की गई सामग्री और संबंधित रूट संरचना तत्व मिलेगा।

```csharp
// टैग की गई सामग्री और मूल संरचना तत्व प्राप्त करें
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

हमें पीडीएफ दस्तावेज़ की टैग की गई सामग्री और संबंधित रूट संरचना तत्व मिला।

## चरण 4: टैग किए गए पीडीएफ दस्तावेज़ के लिए शीर्षक सेट करना

अब टैग किए गए पीडीएफ दस्तावेज़ के लिए शीर्षक सेट करें।

```csharp
// टैग किए गए पीडीएफ दस्तावेज़ के लिए शीर्षक परिभाषित करें
taggedContent.SetTitle("Document with images");
```

हमने टैग किए गए पीडीएफ दस्तावेज़ के लिए शीर्षक निर्धारित किया है।

## चरण 5: छवि पर वैकल्पिक टेक्स्ट और बाउंडिंग बॉक्स निर्दिष्ट करें

अब, प्रत्येक छवि तत्व के लिए, हम वैकल्पिक टेक्स्ट और एक बाउंडिंग बॉक्स निर्दिष्ट करेंगे।

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // छवि को वैकल्पिक पाठ निर्दिष्ट करें
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // बाउंडिंग बॉक्स बनाएं और असाइन करें (बीबॉक्स)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

हमने पीडीएफ दस्तावेज़ में प्रत्येक छवि तत्व के लिए वैकल्पिक टेक्स्ट और एक बाउंडिंग बॉक्स निर्दिष्ट किया है।

## चरण 6: स्पैन तत्व को पैराग्राफ में ले जाना

अब स्पैन तत्व को पैराग्राफ में ले जाएँ।

```csharp
// स्पैन तत्व को पैराग्राफ में ले जाएं (पहले टीडी में गलत स्पैन और पैराग्राफ ढूंढें)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// पैराग्राफ में स्पैन तत्व को स्थानांतरित करें
spanElement.ChangeParentElement(paragraph);
```

हमने स्पैन तत्व को निर्दिष्ट पैराग्राफ में स्थानांतरित कर दिया।

## चरण 7: संशोधित पीडीएफ दस्तावेज़ को सहेजना

अब जब हमने आवश्यक परिवर्तन कर लिए हैं, तो हम संशोधित पीडीएफ दस्तावेज़ को सहेज लेंगे।

```csharp
// पीडीएफ दस्तावेज़ सहेजें
document. Save(outFile);
```

हमने संशोधित पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजा है।

### .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ में टैग छवि के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// दस्तावेज़ खोलें
Document document = new Document(inFile);

// टैग की गई सामग्री और मूल संरचना तत्व प्राप्त करता है
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// टैग किए गए पीडीएफ दस्तावेज़ के लिए शीर्षक सेट करें
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// चित्र के लिए वैकल्पिक पाठ सेट करें
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox विशेषता बनाएं और सेट करें
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// स्पैन एलिमेंट को पैराग्राफ में ले जाएं (पहले टीडी में गलत स्पैन और पैराग्राफ ढूंढें)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// स्पैन एलिमेंट को पैराग्राफ में ले जाएँ
spanElement.ChangeParentElement(paragraph);

// दस्तावेज़ सहेजें
document.Save(outFile);

//दस्तावेज़ के लिए पीडीएफ/यूए अनुपालन की जाँच करना
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ में एक छवि को कैसे चिह्नित किया जाए। अब आप अपने पीडीएफ दस्तावेज़ों में टैग जोड़ने और छवियों में संपादन करने के लिए Aspose.PDF का उपयोग कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ में छवियों को टैग करने पर इस ट्यूटोरियल का मुख्य उद्देश्य क्या है?

उ: इस ट्यूटोरियल का प्राथमिक लक्ष्य .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ के भीतर एक छवि को चिह्नित करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करना है। ट्यूटोरियल चरण-दर-चरण निर्देश और C# स्रोत कोड उदाहरण प्रदान करता है ताकि आपको यह समझने में मदद मिल सके कि छवियों को वैकल्पिक टेक्स्ट और बाउंडिंग बॉक्स कैसे निर्दिष्ट करें, दस्तावेज़ के भीतर तत्वों को कैसे स्थानांतरित करें और छवियों में टैग कैसे जोड़ें।

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके PDF में छवियों को टैग करने के इस ट्यूटोरियल का अनुसरण करने के लिए क्या शर्तें हैं?

उ: शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपना विकास वातावरण स्थापित कर लिया है। इसमें Aspose.PDF लाइब्रेरी को स्थापित करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

#### प्रश्न: मैं मौजूदा पीडीएफ दस्तावेज़ को कैसे खोल सकता हूं और .NET के लिए Aspose.PDF का उपयोग करके उसकी टैग की गई सामग्री तक कैसे पहुंच सकता हूं?

उ: ट्यूटोरियल सी# स्रोत कोड उदाहरण प्रदान करता है जो दर्शाता है कि .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ को कैसे खोलें और आगे के हेरफेर के लिए इसकी टैग की गई सामग्री तक कैसे पहुंचें।

#### प्रश्न: पीडीएफ दस्तावेज़ में छवियों के लिए वैकल्पिक टेक्स्ट और बाउंडिंग बॉक्स निर्दिष्ट करने का उद्देश्य क्या है?

उ: छवियों के लिए वैकल्पिक पाठ और बाउंडिंग बॉक्स निर्दिष्ट करने से छवियों के लिए वर्णनात्मक पाठ प्रदान करके और दस्तावेज़ के भीतर उनके लेआउट और स्थिति को परिभाषित करके पहुंच में वृद्धि होती है। यह जानकारी स्क्रीन रीडर और अन्य सहायक तकनीकों के लिए महत्वपूर्ण है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए PDF दस्तावेज़ का शीर्षक कैसे सेट कर सकता हूं?

उ: ट्यूटोरियल में C# स्रोत कोड उदाहरण शामिल हैं जो बताते हैं कि .NET के लिए Aspose.PDF का उपयोग करके टैग किए गए पीडीएफ दस्तावेज़ के लिए शीर्षक कैसे सेट किया जाए।

#### प्रश्न: पीडीएफ दस्तावेज़ में तत्वों को स्थानांतरित करने की प्रक्रिया में क्या शामिल है?

उ: पीडीएफ दस्तावेज़ के भीतर तत्वों को स्थानांतरित करने में किसी विशेष तत्व के मूल तत्व को बदलना शामिल है। इस ट्यूटोरियल में, आप सीखेंगे कि किसी तालिका के भीतर एक स्पैन तत्व को एक निर्दिष्ट पैराग्राफ तत्व में कैसे स्थानांतरित किया जाए।

#### प्रश्न: मैं छवियों में टैग जोड़ने और संपादन करने के बाद संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उ: एक बार जब आप टैग जोड़ लेते हैं, वैकल्पिक पाठ निर्दिष्ट कर देते हैं, बाउंडिंग बॉक्स सेट कर लेते हैं, और पीडीएफ दस्तावेज़ में संपादन कर लेते हैं, तो आप संशोधित पीडीएफ दस्तावेज़ को सहेजने के लिए दिए गए सी# स्रोत कोड उदाहरणों का उपयोग कर सकते हैं।`Save()` तरीका।

#### प्रश्न: ट्यूटोरियल में दिए गए नमूना स्रोत कोड का उद्देश्य क्या है?

उत्तर: नमूना स्रोत कोड .NET के लिए Aspose.PDF का उपयोग करके छवि टैगिंग और हेरफेर को लागू करने के लिए एक व्यावहारिक संदर्भ के रूप में कार्य करता है। आप इस कोड को शुरुआती बिंदु के रूप में उपयोग कर सकते हैं और अपनी विशिष्ट आवश्यकताओं के अनुरूप इसे संशोधित कर सकते हैं।

#### प्रश्न: क्या मैं इन तकनीकों को पीडीएफ दस्तावेज़ में केवल छवियों के अलावा अन्य प्रकार के तत्वों पर भी लागू कर सकता हूं?

उत्तर: हां, इस ट्यूटोरियल में प्रदर्शित तकनीकों को पीडीएफ दस्तावेज़ के भीतर विभिन्न प्रकार के तत्वों के साथ काम करने के लिए अनुकूलित किया जा सकता है। आप पाठ, तालिकाओं और अन्य जैसे अन्य तत्वों को टैग और हेरफेर करने के लिए समान सिद्धांत लागू कर सकते हैं।

#### प्रश्न: मैं संशोधित पीडीएफ दस्तावेज़ के पीडीएफ/यूए अनुपालन को कैसे सत्यापित कर सकता हूं?

 उ: ट्यूटोरियल सी# स्रोत कोड उदाहरण प्रदान करता है जो दिखाता है कि संशोधित पीडीएफ दस्तावेज़ के पीडीएफ/यूए अनुपालन को कैसे मान्य किया जाए।`Validate()` विधि और XML रिपोर्ट तैयार करना।

#### प्रश्न: पीडीएफ दस्तावेज़ों के साथ काम करने के लिए .NET के लिए Aspose.PDF क्या अन्य सुविधाएँ प्रदान करता है?

उत्तर: .NET के लिए Aspose.PDF पीडीएफ दस्तावेज़ों के साथ काम करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें टेक्स्ट हेरफेर, छवि प्रविष्टि, तालिका निर्माण, फॉर्म फ़ील्ड प्रबंधन, डिजिटल हस्ताक्षर, एनोटेशन और बहुत कुछ शामिल है। आगे की खोज के लिए आधिकारिक दस्तावेज़ीकरण और संसाधनों से परामर्श लें।