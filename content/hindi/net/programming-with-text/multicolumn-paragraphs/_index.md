---
title: पीडीएफ फाइल में बहुस्तंभ पैराग्राफ
linktitle: पीडीएफ फाइल में बहुस्तंभ पैराग्राफ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में बहुस्तंभ पैराग्राफ़ के साथ काम करना सीखें।
type: docs
weight: 250
url: /hi/net/programming-with-text/multicolumn-paragraphs/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF फ़ाइल में मल्टीकॉलम पैराग्राफ़ के साथ कैसे काम किया जाए। हम दिए गए C# सोर्स कोड का उपयोग करके मल्टीकॉलम पैराग्राफ़ में हेरफेर करने और उन तक पहुँचने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आपकी इनपुट पीडीएफ फाइल स्थित है।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपनी पीडीएफ फाइल के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ लोड करें

 इसके बाद, हम इनपुट पीडीएफ दस्तावेज़ को लोड करते हैं`Document` Aspose.PDF लाइब्रेरी से क्लास.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## चरण 3: बहुस्तंभ पैराग्राफ तक पहुंचें

 हम उपयोग करते हैं`ParagraphAbsorber` पीडीएफ दस्तावेज़ में पैराग्राफ़ को समझने और देखने के लिए क्लास का उपयोग करें। फिर हम पेज मार्कअप प्राप्त करते हैं और मल्टीकॉलम पैराग्राफ़ तक पहुँचते हैं।

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## चरण 4: बहुस्तंभ पैराग्राफ़ के साथ काम करें

हम बहुस्तंभ संरचना के भीतर विशिष्ट अनुभागों और पैराग्राफों तक पहुंचते हैं और उनके पाठ को प्रिंट करते हैं।

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// किसी अनुभाग के अंतिम पैराग्राफ तक पहुँचना
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// किसी अनुभाग के पहले पैराग्राफ तक पहुँचना
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// बहुस्तंभ पैराग्राफ़ सक्षम करना
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// बहुस्तंभ पैराग्राफ़ सक्षम करने के बाद किसी अनुभाग में अंतिम पैराग्राफ़ तक पहुँचना
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// बहुस्तंभ पैराग्राफ़ सक्षम करने के बाद किसी अनुभाग में पहले पैराग्राफ़ तक पहुँचना
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### .NET के लिए Aspose.PDF का उपयोग करके बहुस्तंभ पैराग्राफ़ के लिए नमूना स्रोत कोड 
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

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में मल्टीकॉलम पैराग्राफ़ के साथ कैसे काम किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप PDF दस्तावेज़ में मल्टीकॉलम पैराग्राफ़ तक पहुँच सकते हैं और उनमें हेरफेर कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "मल्टीकॉलम पैराग्राफ इन पीडीएफ फाइल" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "मल्टीकॉलम पैराग्राफ़ इन पीडीएफ़ फ़ाइल" ट्यूटोरियल यह दर्शाता है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में मल्टीकॉलम पैराग्राफ़ के साथ कैसे काम किया जाए। ट्यूटोरियल मल्टीकॉलम पैराग्राफ़ तक पहुँचने और उन्हें मैनिपुलेट करने में आपकी मदद करने के लिए चरण-दर-चरण मार्गदर्शिका और C# स्रोत कोड प्रदान करता है।

#### प्रश्न: मैं PDF दस्तावेज़ में बहुस्तंभ पैराग्राफ़ के साथ काम क्यों करना चाहूंगा?

उत्तर: मल्टीकॉलम पैराग्राफ़ के साथ काम करने से आप अपने PDF दस्तावेज़ों के लिए ज़्यादा परिष्कृत और आकर्षक लेआउट बना सकते हैं। मल्टीकॉलम पैराग्राफ़ का इस्तेमाल अक्सर पठनीयता में सुधार करने और सामग्री की समग्र प्रस्तुति को बढ़ाने के लिए किया जाता है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे स्थापित करूँ?

उत्तर: दस्तावेज़ निर्देशिका सेट अप करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` चर को उस निर्देशिका के पथ के साथ जोड़ें जहां आपकी इनपुट पीडीएफ फाइल स्थित है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ कैसे लोड करूं और बहुस्तंभ पैराग्राफ तक कैसे पहुंचूं?

 उत्तर: ट्यूटोरियल में,`Document` क्लास का उपयोग इनपुट पीडीएफ दस्तावेज़ को लोड करने के लिए किया जाता है।`ParagraphAbsorber` फिर पीडीएफ दस्तावेज़ में पैराग्राफ़ को समझने और देखने के लिए क्लास का उपयोग किया जाता है।`PageMarkup` क्लास का उपयोग बहुस्तंभ पैराग्राफ तक पहुंचने के लिए किया जाता है।

#### प्रश्न: मैं विशिष्ट बहुस्तंभ पैराग्राफ़ों के साथ कैसे काम करूं?

 उत्तर: यह ट्यूटोरियल आपको मल्टीकॉलम संरचना के भीतर विशिष्ट अनुभागों और पैराग्राफों तक पहुंचने की प्रक्रिया के माध्यम से मार्गदर्शन करता है।`MarkupSection` और`MarkupParagraph` यह दर्शाता है कि इन पैराग्राफों के पाठ को कैसे प्रिंट किया जाए।

#### प्रश्न: मैं बहुस्तंभ पैराग्राफ़ कैसे सक्षम करूँ?

 उत्तर: बहुस्तंभ पैराग्राफ़ सक्षम करने के लिए, आप सेट कर सकते हैं`IsMulticolumnParagraphsAllowed` की संपत्ति`PageMarkup` करने के लिए वस्तु`true`.

#### प्रश्न: इस ट्यूटोरियल का अपेक्षित आउटपुट क्या है?

उत्तर: ट्यूटोरियल का पालन करने और दिए गए C# कोड को निष्पादित करने के बाद, आप PDF दस्तावेज़ में मल्टीकॉलम पैराग्राफ़ तक पहुँच और उसमें हेरफेर करने में सक्षम होंगे। ट्यूटोरियल दर्शाता है कि मल्टीकॉलम संरचना के भीतर विभिन्न अनुभागों और पैराग्राफ़ के साथ कैसे काम किया जाए।

#### प्रश्न: क्या मैं बहुस्तंभ पैराग्राफ़ के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: यह ट्यूटोरियल मल्टीकॉलम पैराग्राफ़ की सामग्री तक पहुँचने और उसमें हेरफेर करने पर ध्यान केंद्रित करता है, न कि उनके स्वरूप पर। हालाँकि, आप अपने PDF दस्तावेज़ की उपस्थिति को अनुकूलित करने के लिए Aspose.PDF लाइब्रेरी की अन्य सुविधाओं का उपयोग कर सकते हैं, जैसे कि फ़ॉन्ट, रंग और शैलियाँ सेट करना।