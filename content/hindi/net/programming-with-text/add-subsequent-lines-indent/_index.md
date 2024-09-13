---
title: पीडीएफ फाइल में अगली पंक्तियों का इंडेंट जोड़ें
linktitle: पीडीएफ फाइल में अगली पंक्तियों का इंडेंट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पाठ में बाद की पंक्तियों को इंडेंट करना सीखें।
type: docs
weight: 60
url: /hi/net/programming-with-text/add-subsequent-lines-indent/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट में बाद की पंक्तियों को इंडेंट करने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को प्रदर्शित करता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप बाद की पंक्तियों में इंडेंट जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: एक नया दस्तावेज़ ऑब्जेक्ट बनाएँ
 एक नया उदाहरण बनाएँ`Document` निम्न कोड पंक्ति जोड़कर ऑब्जेक्ट बनाएँ:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में एक नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages` संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## चरण 6: बाद की पंक्तियों के इंडेंट के साथ एक टेक्स्टफ़्रेगमेंट बनाएँ
 एक उदाहरण बनाना`TextFragment` ऑब्जेक्ट और वांछित पाठ प्रदान करें। प्रदान किए गए कोड में, पाठ को चर को सौंपा गया है`text` . फिर, आरंभ करें`TextFormattingOptions` के लिए`TextFragment` और निर्दिष्ट करें`SubsequentLinesIndent` कीमत।

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## चरण 7: पृष्ठ पर टेक्स्टफ़्रेगमेंट जोड़ें
 जोड़ें`TextFragment` पृष्ठ के पैराग्राफ संग्रह पर आपत्ति।

```csharp
page.Paragraphs.Add(text);
```

## चरण 8: अतिरिक्त पंक्तियों के लिए चरण 6 और 7 को दोहराएँ
उसी इंडेंट के साथ अगली पंक्तियाँ जोड़ने के लिए, प्रत्येक पंक्ति के लिए चरण 6 और 7 को दोहराएँ। आवश्यकतानुसार टेक्स्ट सामग्री को अपडेट करें।

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## चरण 9: पीडीएफ दस्तावेज़ सहेजें
 पीडीएफ दस्तावेज़ को सेव करने के लिए निम्न का उपयोग करें:`Save` की विधि`Document` आउटपुट फ़ाइल पथ निर्दिष्ट करें.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### .NET के लिए Aspose.PDF का उपयोग करके अनुवर्ती पंक्तियों का इंडेंट जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// नया दस्तावेज़ ऑब्जेक्ट बनाएँ
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//पाठ खंड के लिए TextFormattingOptions आरंभ करें और SubsequentLinesIndent मान निर्दिष्ट करें
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट में इंडेंट की गई अगली पंक्तियों को सफलतापूर्वक जोड़ दिया है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

उत्तर: यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट में बाद की पंक्तियों को इंडेंट करने के तरीके पर एक व्यापक गाइड प्रदान करता है। इसमें इसे प्राप्त करने के लिए आवश्यक चरणों को स्पष्ट करने के लिए C# स्रोत कोड उदाहरण शामिल हैं।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने होंगे?

उत्तर: कोड फ़ाइल में जहां आप बाद की पंक्तियों में इंडेंट जोड़ना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं दस्तावेज़ ऑब्जेक्ट कैसे बनाऊं?

 उत्तर: चरण 4 में, आप एक नया इन्स्टेन्सिएट करेंगे`Document` निम्न कोड लाइन का उपयोग करके ऑब्जेक्ट बनाएँ:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### प्रश्न: मैं दस्तावेज़ में पृष्ठ कैसे जोड़ूं?

 उत्तर: चरण 5 में, आप दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### प्रश्न: मैं पाठ में अगली पंक्तियों का इंडेंट कैसे जोड़ सकता हूँ?

 उत्तर: चरण 6 में, आप एक बनाएंगे`TextFragment` ऑब्जेक्ट चुनें और उसे मनचाहा टेक्स्ट असाइन करें। फिर, आप आरंभ करेंगे`TextFormattingOptions` के लिए`TextFragment` और निर्दिष्ट करें`SubsequentLinesIndent` कीमत:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### प्रश्न: मैं PDF दस्तावेज़ में TextFragment कैसे जोड़ूं?

 उत्तर: चरण 7 में, आप जोड़ेंगे`TextFragment` वस्तु (`text`) को पृष्ठ के पैराग्राफ संग्रह में जोड़ें:

```csharp
page.Paragraphs.Add(text);
```

#### प्रश्न: क्या मैं अतिरिक्त लाइनों के लिए प्रक्रिया दोहरा सकता हूँ?

उत्तर: हां, चरण 8 में, आप नई इंडेंट बनाकर समान इंडेंट वाली अतिरिक्त पंक्तियों के लिए प्रक्रिया को दोहरा सकते हैं।`TextFragment` ऑब्जेक्ट्स को चुनना और उन्हें पृष्ठ के पैराग्राफ संग्रह में जोड़ना।

#### प्रश्न: मैं परिणामी पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: बाद की पंक्तियों के इंडेंट के साथ पाठ जोड़ने के बाद, का उपयोग करें`Save` की विधि`Document` पीडीएफ दस्तावेज़ को सहेजने के लिए ऑब्जेक्ट:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके बाद की पंक्तियों को इंडेंट करके PDF दस्तावेज़ में टेक्स्ट की पठनीयता को कैसे बढ़ाया जाए। यह तकनीक विभिन्न प्रकार के दस्तावेज़ों और रिपोर्टों के लिए उपयोगी हो सकती है।