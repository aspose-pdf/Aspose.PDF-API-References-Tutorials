---
title: शीर्षलेख पाद लेख अनुभाग इनलाइन में छवि और पृष्ठ संख्या
linktitle: शीर्षलेख पाद लेख अनुभाग इनलाइन में छवि और पृष्ठ संख्या
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ इनलाइन पैराग्राफ का उपयोग करके शीर्ष लेख और पाद लेख में छवि और पृष्ठ संख्या जोड़ने का तरीका जानें।
type: docs
weight: 120
url: /hi/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ के हेडर और फुटर अनुभाग में छवि और पेज नंबर जोड़ने के तरीके के बारे में चरण दर चरण मार्गदर्शन करेंगे। हम एक पेज बनाने, हेडर और फुटर सेट करने, पीडीएफ दस्तावेज़ के हेडर में इनलाइन पैराग्राफ का उपयोग करके छवि और टेक्स्ट जोड़ने के लिए दिए गए सी # स्रोत कोड का उपयोग करेंगे।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- एक स्थापित .NET विकास वातावरण।
- .NET के लिए Aspose.PDF लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में संदर्भित की गई।

## चरण 2: पीडीएफ दस्तावेज़ और पेज बनाना

पहला कदम पीडीएफ दस्तावेज़ में एक नया दस्तावेज़ ऑब्जेक्ट और एक पेज बनाना है। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// एक नया दस्तावेज़ ऑब्जेक्ट बनाएँ
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// दस्तावेज़ में एक पेज बनाएं
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

उपरोक्त कोड पीडीएफ दस्तावेज़ में एक नया दस्तावेज़ ऑब्जेक्ट और एक खाली पृष्ठ बनाता है।

## चरण 3: एक छवि और इनलाइन टेक्स्ट के साथ हेडर जोड़ना

अब जब पेज बन गया है, तो हम इनलाइन पैराग्राफ का उपयोग करके एक छवि और टेक्स्ट के साथ एक हेडर अनुभाग जोड़ सकते हैं। ऐसे:

```csharp
// एक हेडर अनुभाग बनाएं
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// पेज हेडर सेट करें
page. Header = header;

// पहले इनलाइन टेक्स्ट के लिए एक TextFragment ऑब्जेक्ट बनाएं
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// पाठ का रंग निर्दिष्ट करें
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// छवि के लिए एक छवि ऑब्जेक्ट बनाएं
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// छवि पथ सेट करें
image1.File = dataDir + "aspose-logo.jpg";

// छवि के आयाम परिभाषित करें
image1.FixWidth = 50;
image1.FixHeight = 20;

// इंगित करें कि पहला इनलाइन टेक्स्ट एक छवि है
image1.IsInLineParagraph = true;

// दूसरा इनलाइन टेक्स्ट बनाएं
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// हेडर में आइटम जोड़ें
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

उपरोक्त कोड एक हेडर सेक्शन बनाता है, इस सेक्शन के साथ पेज हेडर सेट करता है, इनलाइन टेक्स्ट और एक इनलाइन इमेज ऑब्जेक्ट के साथ एक टेक्स्टफ्रैगमेंट जोड़ता है।

## चरण 4: संशोधित पीडीएफ दस्तावेज़ को सहेजना

एक बार छवि और इनलाइन टेक्स्ट वाला हेडर जुड़ जाने के बाद, हम संशोधित पीडीएफ दस्तावेज़ को सहेज सकते हैं। ऐसे:

```csharp
// संशोधित पीडीएफ दस्तावेज़ सहेजें
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

उपरोक्त कोड संपादित पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजता है।

### .NET के लिए Aspose.PDF का उपयोग करके हेडर फुटर सेक्शन इनलाइन में छवि और पेज नंबर के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// किसी दस्तावेज़ ऑब्जेक्ट को उसके खाली कंस्ट्रक्टर को कॉल करके इंस्टेंट करें
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// पीडीएफ ऑब्जेक्ट में एक पेज बनाएं
Aspose.Pdf.Page page = pdf1.Pages.Add();

// दस्तावेज़ का हेडर अनुभाग बनाएं
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// पीडीएफ फाइल के लिए हेडर सेट करें
page.Header = header;

// एक टेक्स्ट ऑब्जेक्ट बनाएं
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// रंग निर्दिष्ट करें
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// अनुभाग में एक छवि ऑब्जेक्ट बनाएं
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// छवि फ़ाइल का पथ सेट करें
image1.File = dataDir + "aspose-logo.jpg";

// छवि चौड़ाई जानकारी सेट करें
image1.FixWidth = 50;
image1.FixHeight = 20;

// इंगित करें कि seg1 का InlineParagraph एक छवि है।
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// पीडीएफ को सेव करें
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## निष्कर्ष

बधाई हो! आपने सीखा है कि .NET के लिए Aspose.PDF के साथ इनलाइन पैराग्राफ का उपयोग करके पीडीएफ दस्तावेज़ के शीर्षलेख और पादलेख अनुभाग में एक छवि और पृष्ठ संख्या कैसे जोड़ें। अब आप अपने पीडीएफ दस्तावेज़ों के शीर्षलेख और पादलेख को लचीले ढंग से अनुकूलित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ के हेडर में छवि और टेक्स्ट जोड़ने के लिए इनलाइन पैराग्राफ का उपयोग करने का क्या फायदा है?

उ: इनलाइन पैराग्राफ का उपयोग करने से आप छवियों और पाठ को एक ही पैराग्राफ में सहजता से एकीकृत कर सकते हैं, जिससे उनके प्लेसमेंट और फ़ॉर्मेटिंग पर सटीक नियंत्रण मिलता है। यह विधि दृश्य तत्वों के साथ अनुकूलित हेडर बनाने के लिए विशेष रूप से उपयोगी है।

#### प्रश्न: प्रदान किया गया C# स्रोत कोड पीडीएफ दस्तावेज़ में हेडर के लिए इनलाइन पैराग्राफ कैसे प्राप्त करता है?

उ: प्रदान किया गया कोड दर्शाता है कि एक पीडीएफ दस्तावेज़ कैसे बनाया जाए, एक पेज कैसे जोड़ा जाए और इनलाइन पैराग्राफ का उपयोग करके हेडर को कैसे अनुकूलित किया जाए। यह इनलाइन टेक्स्ट, एक इनलाइन इमेज और एक अन्य इनलाइन टेक्स्टफ्रैगमेंट के साथ एक टेक्स्टफ्रैगमेंट जोड़ता है।

#### प्रश्न: मैं हेडर में इनलाइन टेक्स्ट का रंग कैसे निर्दिष्ट करूं?

 ए: इनलाइन टेक्स्ट का रंग का उपयोग करके निर्दिष्ट किया जाता है`ForegroundColor` की संपत्ति`TextState` की`TextFragment` वस्तु।

#### प्रश्न: क्या मैं हेडर में इनलाइन छवि के आयामों को समायोजित कर सकता हूँ?

 उत्तर: हां, आप इसका उपयोग करके इनलाइन छवि के आयामों को समायोजित कर सकते हैं`FixWidth` और`FixHeight` के गुण`Image` वस्तु। यह आपको हेडर के भीतर छवि की चौड़ाई और ऊंचाई को नियंत्रित करने की अनुमति देता है।

#### प्रश्न: क्या मैं हेडर में अतिरिक्त इनलाइन तत्व, जैसे हाइपरलिंक या विभिन्न फ़ॉन्ट शैलियाँ शामिल कर सकता हूँ?

 उ: हाँ, आप और अधिक बनाकर हेडर में अतिरिक्त इनलाइन तत्व शामिल कर सकते हैं`TextFragment` या`Image` वांछित गुणों वाली वस्तुएँ। यह आपको हाइपरलिंक, विभिन्न फ़ॉन्ट शैलियों, या अन्य दृश्य तत्वों सहित हेडर को और अधिक अनुकूलित करने की अनुमति देता है।

#### प्रश्न: मैं यह कैसे सुनिश्चित कर सकता हूं कि इनलाइन छवि और टेक्स्ट विभिन्न उपकरणों और दर्शकों के बीच ठीक से संरेखित और स्वरूपित रहें?

उत्तर: .NET के लिए Aspose.PDF यह सुनिश्चित करता है कि इनलाइन छवियां और टेक्स्ट ठीक से संरेखित और स्वरूपित हैं, जिसके परिणामस्वरूप विभिन्न उपकरणों और पीडीएफ दर्शकों में एक समान उपस्थिति होती है।

#### प्रश्न: क्या मैं पाद लेख अनुभाग में इनलाइन पैराग्राफ भी लागू कर सकता हूँ?

 उ: हां, आप इनलाइन पैराग्राफ का उपयोग करने की एक ही तकनीक को पादलेख अनुभाग में बनाकर लागू कर सकते हैं`Footer` ऑब्जेक्ट बनाना और उसमें टेक्स्ट और इमेज जैसे इनलाइन तत्व जोड़ना।

#### प्रश्न: क्या इनलाइन पैराग्राफ को अन्य हेडर या फ़ूटर अनुकूलन विधियों के साथ जोड़ना संभव है?

उत्तर: हाँ, आप अधिक जटिल और अनुकूलित हेडर या फ़ूटर डिज़ाइन बनाने के लिए .NET के लिए Aspose.PDF द्वारा प्रदान किए गए अन्य हेडर या फ़ूटर अनुकूलन विधियों के साथ इनलाइन पैराग्राफ को जोड़ सकते हैं।

#### प्रश्न: यदि आवश्यक हो तो क्या मैं हेडर से इनलाइन तत्वों को हटा या साफ़ कर सकता हूँ?

 उ: हां, आप सामग्री को संशोधित करके इनलाइन तत्वों को हटा या साफ़ कर सकते हैं`HeaderFooter` आपत्ति करना और संबंधित इनलाइन पैराग्राफ को हटाना।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ के विशिष्ट पृष्ठों पर इनलाइन पैराग्राफ कैसे लागू कर सकता हूं?

 उ: विशिष्ट पृष्ठों पर इनलाइन पैराग्राफ लागू करने के लिए, आप अलग-अलग बना सकते हैं`HeaderFooter` प्रत्येक पृष्ठ के लिए ऑब्जेक्ट बनाएं और उन्हें इसका उपयोग करके असाइन करें`Header` संबंधित की संपत्ति`Aspose.Pdf.Page` वस्तुएं.