---
title: पीडीएफ फाइल में मल्टीकॉलम पैराग्राफ
linktitle: पीडीएफ फाइल में मल्टीकॉलम पैराग्राफ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में मल्टीकॉलम पैराग्राफ के साथ काम करना सीखें।
type: docs
weight: 250
url: /hi/net/programming-with-text/multicolumn-paragraphs/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में मल्टीकॉलम पैराग्राफ के साथ कैसे काम किया जाए। हम दिए गए C# स्रोत कोड का उपयोग करके मल्टीकॉलम पैराग्राफ में हेरफेर करने और उन तक पहुंचने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित किया गया।
- C# प्रोग्रामिंग की बुनियादी समझ।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस निर्देशिका के लिए पथ सेट करना होगा जहां आपकी इनपुट पीडीएफ फाइल स्थित है। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` आपकी पीडीएफ फाइल के पथ के साथ परिवर्तनीय।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ लोड करें

 इसके बाद, हम इसका उपयोग करके इनपुट पीडीएफ दस्तावेज़ लोड करते हैं`Document` Aspose.PDF लाइब्रेरी से कक्षा।

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## चरण 3: मल्टीकॉलम पैराग्राफ तक पहुंचें

 हम उपयोग करते हैं`ParagraphAbsorber` पीडीएफ दस्तावेज़ में पैराग्राफ को आत्मसात करने और देखने के लिए कक्षा। फिर हम पेज मार्कअप पुनर्प्राप्त करते हैं और मल्टीकॉलम पैराग्राफ तक पहुंचते हैं।

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## चरण 4: मल्टीकॉलम पैराग्राफ के साथ काम करें

हम मल्टीकॉलम संरचना के भीतर विशिष्ट अनुभागों और पैराग्राफों तक पहुंचते हैं और उनके पाठ को प्रिंट करते हैं।

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// किसी अनुभाग में अंतिम पैराग्राफ तक पहुँचना
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// किसी अनुभाग में पहले पैराग्राफ तक पहुँचना
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// बहुस्तंभ पैराग्राफ सक्षम करना
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// बहुस्तंभ अनुच्छेदों को सक्षम करने के बाद किसी अनुभाग में अंतिम अनुच्छेद तक पहुँचना
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

//बहुस्तंभ पैराग्राफ सक्षम करने के बाद किसी अनुभाग में पहले पैराग्राफ तक पहुँचना
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### .NET के लिए Aspose.PDF का उपयोग करके मल्टीकॉलम पैराग्राफ के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके एक पीडीएफ दस्तावेज़ में मल्टीकॉलम पैराग्राफ के साथ कैसे काम किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप पीडीएफ दस्तावेज़ में मल्टीकॉलम पैराग्राफ तक पहुंच और हेरफेर कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में मल्टीकॉलम पैराग्राफ" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में मल्टीकॉलम पैराग्राफ" ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ में मल्टीकॉलम पैराग्राफ के साथ कैसे काम किया जाए। ट्यूटोरियल आपको मल्टीकॉलम पैराग्राफ तक पहुंचने और उनमें हेरफेर करने में मदद करने के लिए चरण-दर-चरण मार्गदर्शिका और C# स्रोत कोड प्रदान करता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में मल्टीकॉलम पैराग्राफ के साथ काम क्यों करना चाहूंगा?

उ: मल्टीकॉलम पैराग्राफ के साथ काम करने से आप अपने पीडीएफ दस्तावेज़ों के लिए अधिक परिष्कृत और आकर्षक लेआउट बना सकते हैं। पठनीयता में सुधार और सामग्री की समग्र प्रस्तुति को बढ़ाने के लिए अक्सर बहुस्तंभ पैराग्राफ का उपयोग किया जाता है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे सेट करूँ?

उ: दस्तावेज़ निर्देशिका स्थापित करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका के पथ के साथ परिवर्तनीय जहां आपकी इनपुट पीडीएफ फ़ाइल स्थित है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को कैसे लोड करूं और मल्टीकॉलम पैराग्राफ तक कैसे पहुंचूं?

 ए: ट्यूटोरियल में,`Document` इनपुट पीडीएफ दस्तावेज़ को लोड करने के लिए क्लास का उपयोग किया जाता है।`ParagraphAbsorber` फिर कक्षा को पीडीएफ दस्तावेज़ में पैराग्राफ को अवशोषित करने और देखने के लिए नियोजित किया जाता है।`PageMarkup` क्लास का उपयोग मल्टीकॉलम पैराग्राफ तक पहुंचने के लिए किया जाता है।

#### प्रश्न: मैं विशिष्ट बहुस्तंभ अनुच्छेदों के साथ कैसे काम करूँ?

 उ: ट्यूटोरियल आपको मल्टीकॉलम संरचना के भीतर विशिष्ट अनुभागों और पैराग्राफों तक पहुंचने की प्रक्रिया के माध्यम से मार्गदर्शन करता है`MarkupSection` और`MarkupParagraph` कक्षाएं. यह दर्शाता है कि इन अनुच्छेदों के पाठ को कैसे मुद्रित किया जाए।

#### प्रश्न: मैं मल्टीकॉलम पैराग्राफ कैसे सक्षम करूं?

 उ: मल्टीकॉलम पैराग्राफ को सक्षम करने के लिए, आप सेट कर सकते हैं`IsMulticolumnParagraphsAllowed` की संपत्ति`PageMarkup` करने के लिए वस्तु`true`.

#### प्रश्न: इस ट्यूटोरियल का अपेक्षित आउटपुट क्या है?

उ: ट्यूटोरियल का पालन करने और दिए गए सी# कोड को निष्पादित करने के बाद, आप पीडीएफ दस्तावेज़ में मल्टीकॉलम पैराग्राफ तक पहुंचने और उनमें हेरफेर करने में सक्षम होंगे। ट्यूटोरियल दर्शाता है कि मल्टीकॉलम संरचना के भीतर विभिन्न अनुभागों और पैराग्राफों के साथ कैसे काम किया जाए।

#### प्रश्न: क्या मैं बहुस्तंभ पैराग्राफों के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: यह ट्यूटोरियल मल्टीकॉलम पैराग्राफों की उपस्थिति के बजाय उनकी सामग्री तक पहुंचने और हेरफेर करने पर केंद्रित है। हालाँकि, आप अपने पीडीएफ दस्तावेज़ की उपस्थिति को अनुकूलित करने के लिए Aspose.PDF लाइब्रेरी की अन्य सुविधाओं का उपयोग कर सकते हैं, जैसे फ़ॉन्ट, रंग और शैली सेट करना।