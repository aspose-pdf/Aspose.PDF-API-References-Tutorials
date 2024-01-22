---
title: पीडीएफ फाइल में अनुवर्ती पंक्तियाँ इंडेंट जोड़ें
linktitle: पीडीएफ फाइल में अनुवर्ती पंक्तियाँ इंडेंट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में टेक्स्ट में इंडेंट के बाद की पंक्तियों को जोड़ने का तरीका जानें।
type: docs
weight: 60
url: /hi/net/programming-with-text/add-subsequent-lines-indent/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में टेक्स्ट में इंडेंट के बाद की पंक्तियों को जोड़ने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप बाद की लाइनें इंडेंट जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निर्देश का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: एक नया दस्तावेज़ ऑब्जेक्ट बनाएं
 एक नया त्वरित करें`Document` कोड की निम्नलिखित पंक्ति जोड़कर ऑब्जेक्ट करें:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 का उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ें`Add` की विधि`Pages`संग्रह। दिए गए कोड में, नया पेज वेरिएबल को सौंपा गया है`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## चरण 6: अनुवर्ती पंक्तियों के इंडेंट के साथ एक टेक्स्टफ़्रैगमेंट बनाएं
 त्वरित करें ए`TextFragment` ऑब्जेक्ट करें और वांछित पाठ प्रदान करें। दिए गए कोड में, टेक्स्ट वेरिएबल को सौंपा गया है`text` . फिर, आरंभ करें`TextFormattingOptions` के लिए`TextFragment`और निर्दिष्ट करें`SubsequentLinesIndent` कीमत।

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## चरण 7: पेज पर टेक्स्टफ्रैगमेंट जोड़ें
 जोड़ें`TextFragment` पृष्ठ के अनुच्छेद संग्रह पर आपत्ति।

```csharp
page.Paragraphs.Add(text);
```

## चरण 8: अतिरिक्त लाइनों के लिए चरण 6 और 7 दोहराएँ
समान इंडेंट के साथ अगली पंक्तियाँ जोड़ने के लिए, प्रत्येक पंक्ति के लिए चरण 6 और 7 दोहराएँ। आवश्यकतानुसार पाठ्य सामग्री को अद्यतन करें।

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
 का उपयोग करके पीडीएफ दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु। आउटपुट फ़ाइल पथ निर्दिष्ट करें.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### .NET के लिए Aspose.PDF का उपयोग करके अनुवर्ती पंक्तियाँ इंडेंट जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// नया दस्तावेज़ ऑब्जेक्ट बनाएँ
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// टेक्स्ट फ़्रैगमेंट के लिए TextFormattingOptions प्रारंभ करें और SubsequentLinesIndent मान निर्दिष्ट करें
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
आपने .NET के लिए Aspose.PDF का उपयोग करके पाठ में अनुवर्ती इंडेंट पंक्तियों को सफलतापूर्वक जोड़ दिया है। परिणामी पीडीएफ फाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

उ: यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में टेक्स्ट में इंडेंट के बाद की पंक्तियों को जोड़ने के बारे में एक व्यापक गाइड प्रदान करता है। इसे प्राप्त करने के लिए आवश्यक चरणों को दर्शाने के लिए इसमें C# स्रोत कोड उदाहरण शामिल हैं।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने की आवश्यकता है?

उ: कोड फ़ाइल में जहां आप बाद की पंक्तियों के इंडेंट को जोड़ना चाहते हैं, फ़ाइल की शुरुआत में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: कोड में, लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं दस्तावेज़ ऑब्जेक्ट कैसे बनाऊं?

 उ: चरण 4 में, आप एक नया इंस्टेंट करेंगे`Document` कोड की निम्नलिखित पंक्ति का उपयोग करके ऑब्जेक्ट करें:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### प्रश्न: मैं दस्तावेज़ में एक पृष्ठ कैसे जोड़ूँ?

 उ: चरण 5 में, आप इसका उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### प्रश्न: मैं टेक्स्ट में इंडेंट के बाद आने वाली पंक्तियाँ कैसे जोड़ सकता हूँ?

 उ: चरण 6 में, आप एक बनाएंगे`TextFragment` ऑब्जेक्ट करें और उसे वांछित टेक्स्ट असाइन करें। फिर, आप आरंभ करेंगे`TextFormattingOptions` के लिए`TextFragment`और निर्दिष्ट करें`SubsequentLinesIndent` कीमत:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में टेक्स्टफ्रैगमेंट कैसे जोड़ूं?

 उ: चरण 7 में, आप जोड़ देंगे`TextFragment` वस्तु (`text`) पृष्ठ के पैराग्राफ संग्रह के लिए:

```csharp
page.Paragraphs.Add(text);
```

#### प्रश्न: क्या मैं अतिरिक्त लाइनों के लिए प्रक्रिया दोहरा सकता हूँ?

 उ: हां, चरण 8 में, आप नई लाइनें बनाकर उसी इंडेंट के साथ अतिरिक्त लाइनों के लिए प्रक्रिया दोहरा सकते हैं`TextFragment` ऑब्जेक्ट और उन्हें पृष्ठ के पैराग्राफ संग्रह में जोड़ना।

#### प्रश्न: मैं परिणामी पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उत्तर: टेक्स्ट को बाद की लाइनों के इंडेंटेशन के साथ जोड़ने के बाद, इसका उपयोग करें`Save` की विधि`Document` पीडीएफ दस्तावेज़ को सहेजने के लिए ऑब्जेक्ट:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके बाद की पंक्तियाँ इंडेंट जोड़कर एक पीडीएफ दस्तावेज़ में पाठ की पठनीयता को कैसे बढ़ाया जाए। यह तकनीक विभिन्न प्रकार के दस्तावेज़ों और रिपोर्टों के लिए उपयोगी हो सकती है।