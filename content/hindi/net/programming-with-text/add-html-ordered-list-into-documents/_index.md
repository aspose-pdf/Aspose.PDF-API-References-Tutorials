---
title: दस्तावेज़ों में HTML क्रमबद्ध सूची जोड़ें
linktitle: दस्तावेज़ों में HTMLOrdered सूची जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके किसी दस्तावेज़ में HTML क्रमबद्ध सूची जोड़ना सीखें।
type: docs
weight: 30
url: /hi/net/programming-with-text/add-html-ordered-list-into-documents/
---
इस ट्यूटोरियल में, आप सीखेंगे कि दस्तावेज़ में HTML क्रमबद्ध सूची जोड़ने के लिए Aspose.PDF for .NET लाइब्रेरी का उपयोग कैसे करें। प्रदान किया गया कोड इस कार्य को पूरा करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप HTML क्रमबद्ध सूची जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका और आउटपुट फ़ाइल पथ सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

 इसके बाद, वह पंक्ति ढूंढें जिसमें लिखा हो`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` और प्रतिस्थापित करें`"AddHTMLOrderedListIntoDocuments_out.pdf"` अपनी आउटपुट पीडीएफ फाइल के लिए वांछित नाम के साथ।

## चरण 4: एक नया दस्तावेज़ ऑब्जेक्ट बनाएँ
 एक नया उदाहरण बनाएँ`Document` निम्न कोड पंक्ति जोड़कर ऑब्जेक्ट बनाएँ:

```csharp
Document doc = new Document();
```

## चरण 5: HTML सामग्री के साथ एक HtmlFragment ऑब्जेक्ट बनाएँ
 एक उदाहरण बनाना`HtmlFragment` HTML सामग्री वाला ऑब्जेक्ट जिसे आप दस्तावेज़ में जोड़ना चाहते हैं। दिए गए कोड में, HTML सामग्री को वैरिएबल को असाइन किया गया है`t`आप आवश्यकतानुसार HTML सामग्री को संशोधित कर सकते हैं।

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## चरण 6: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में एक नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages`संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`page`.

```csharp
Page page = doc.Pages.Add();
```

## चरण 7: पृष्ठ पर HtmlFragment जोड़ें
 जोड़ें`HtmlFragment` का उपयोग करके पृष्ठ पर आपत्ति करें`Add` की विधि`Paragraphs` संग्रह।

```csharp
page.Paragraphs.Add(t);
```

## चरण 8: पीडीएफ दस्तावेज़ सहेजें
 परिणामी पीडीएफ फाइल को सेव करें`Save` की विधि`Document` ऑब्जेक्ट. चरण 3 में आपके द्वारा सेट किया गया आउटपुट फ़ाइल पथ निर्दिष्ट करें.

```csharp
doc.Save(outFile);
```

### .NET के लिए Aspose.PDF का उपयोग करके दस्तावेज़ों में HTMLOrdered सूची जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// आउटपुट दस्तावेज़ का पथ.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// दस्तावेज़ ऑब्जेक्ट को इंस्टैंशिएट करें
Document doc = new Document();
// HtmlFragment ऑब्जेक्ट को संगत HTML फ़्रैगमेंट के साथ इंस्टैंशिएट करें
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// पेज संग्रह में पेज जोड़ें
Page page = doc.Pages.Add();
// पेज के अंदर HtmlFragment जोड़ें
page.Paragraphs.Add(t);
// परिणामी PDF फ़ाइल सहेजें
doc.Save(outFile);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके दस्तावेज़ में HTML क्रमबद्ध सूची सफलतापूर्वक जोड़ ली है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

HTML सामग्री को अनुकूलित करना और कोड को अपनी विशिष्ट आवश्यकताओं के अनुसार समायोजित करना याद रखें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य आपको Aspose.PDF for .NET लाइब्रेरी का उपयोग करके दस्तावेज़ में HTML क्रमबद्ध सूची जोड़ने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। यह आपको इस कार्य को पूरा करने में मदद करने के लिए चरण-दर-चरण निर्देश और कोड स्निपेट प्रदान करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने होंगे?

उत्तर: आपको अपनी कोड फ़ाइल के शीर्ष पर निम्नलिखित नामस्थान आयात करने होंगे:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका और आउटपुट फ़ाइल पथ कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` अपने दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ। इसके अलावा, लाइन ढूंढें`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` और प्रतिस्थापित करें`"AddHTMLOrderedListIntoDocuments_out.pdf"` अपने इच्छित आउटपुट पीडीएफ फ़ाइल नाम के साथ।

#### प्रश्न: क्या मैं दस्तावेज़ में जोड़ी जाने वाली HTML सामग्री को अनुकूलित कर सकता हूँ?

 उत्तर: बिल्कुल! चरण 5 में, आप एक बनाएंगे`HtmlFragment` ऑब्जेक्ट का नाम`t` जो HTML सामग्री रखता है। आप अपनी आवश्यकताओं के अनुरूप बैकटिक्स के भीतर HTML सामग्री को संशोधित कर सकते हैं।

#### प्रश्न: मैं दस्तावेज़ के किसी पृष्ठ पर HTML क्रमबद्ध सूची कैसे जोड़ूँ?

 उत्तर: चरण 7 में, आप जोड़ेंगे`HtmlFragment` वस्तु (`t` ) का उपयोग करके पेज पर जाएं`Add` की विधि`Paragraphs`यह HTML क्रमबद्ध सूची को दस्तावेज़ में सहजता से एकीकृत कर देगा।

#### प्रश्न: मैं परिणामी पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: HTML सामग्री जोड़ने और उसे पृष्ठ पर व्यवस्थित करने के बाद, आप PDF दस्तावेज़ को सहेज सकते हैं`Save` की विधि`Document` ऑब्जेक्ट। सुनिश्चित करें कि आपने पहले जो आउटपुट फ़ाइल पथ सेट किया था, वह सही है।

#### प्रश्न: क्या आप संदर्भ के लिए नमूना स्रोत कोड का सारांश प्रदान कर सकते हैं?

उत्तर: निश्चित रूप से! इस ट्यूटोरियल में दिए गए नमूना स्रोत कोड का संक्षिप्त संस्करण यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीखा है कि दस्तावेज़ में HTML क्रमबद्ध सूची को शामिल करने के लिए Aspose.PDF for .NET लाइब्रेरी का लाभ कैसे उठाया जाए। इस नए ज्ञान का उपयोग आपके दस्तावेज़ निर्माण और हेरफेर प्रक्रियाओं को बढ़ाने के लिए किया जा सकता है।