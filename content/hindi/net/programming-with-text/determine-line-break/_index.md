---
title: पीडीएफ फाइल में लाइन ब्रेक निर्धारित करें
linktitle: पीडीएफ फाइल में लाइन ब्रेक निर्धारित करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में लाइन ब्रेक निर्धारित करना सीखें।
type: docs
weight: 130
url: /hi/net/programming-with-text/determine-line-break/
---
यह ट्यूटोरियल .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में लाइन ब्रेक निर्धारित करने की प्रक्रिया में आपका मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप लाइन ब्रेक निर्धारित करना चाहते हैं, फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using System.IO;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: एक नया दस्तावेज़ उदाहरण बनाएँ
 एक नया त्वरित करें`Document` कोड की निम्नलिखित पंक्ति जोड़कर ऑब्जेक्ट करें:

```csharp
Document doc = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 का उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ें`Add` की विधि`Pages`संग्रह। दिए गए कोड में, नया पेज वेरिएबल को सौंपा गया है`page`.

```csharp
Page page = doc.Pages.Add();
```

## चरण 6: लाइन ब्रेक के साथ टेक्स्ट टुकड़े जोड़ें
पृष्ठ पर कई पाठ टुकड़े जोड़ने के लिए एक लूप बनाएं, प्रत्येक में लाइन ब्रेक के साथ एक पैराग्राफ हो।

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें और लाइन ब्रेक जानकारी निकालें
 का उपयोग करके पीडीएफ दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु। फिर, का उपयोग करके लाइन ब्रेक जानकारी निकालें`GetNotifications` वांछित पृष्ठ की विधि.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### .NET के लिए Aspose.PDF का उपयोग करके लाइन ब्रेक निर्धारित करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में सफलतापूर्वक लाइन ब्रेक निर्धारित कर लिया है। लाइन ब्रेक जानकारी निकाली गई है और एक टेक्स्ट फ़ाइल में सहेजी गई है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का मुख्य फोकस क्या है?

उत्तर: यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फ़ाइल में लाइन ब्रेक निर्धारित करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को दर्शाता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने चाहिए?

उ: कोड फ़ाइल में जहां आप लाइन ब्रेक निर्धारित करना चाहते हैं, फ़ाइल की शुरुआत में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: कोड में, लाइन ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं एक नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उ: चरण 4 में, आप एक नया इंस्टेंट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट करें।

#### प्रश्न: मैं दस्तावेज़ में एक पृष्ठ कैसे जोड़ूँ?

 उ: चरण 5 में, आप इसका उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं लाइन ब्रेक के साथ टेक्स्ट टुकड़े कैसे जोड़ूं?

उ: चरण 6 में, आप पृष्ठ पर कई टेक्स्ट टुकड़े जोड़ने के लिए एक लूप बनाएंगे, प्रत्येक में लाइन ब्रेक के साथ एक पैराग्राफ होगा।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को कैसे सहेजूं और लाइन ब्रेक जानकारी कैसे निकालूं?

 उ: चरण 7 में, आप इसका उपयोग करके पीडीएफ दस्तावेज़ को सहेजेंगे`Save` की विधि`Document` वस्तु। फिर, आप इसका उपयोग करके लाइन ब्रेक जानकारी निकालेंगे`GetNotifications` वांछित पृष्ठ की विधि बनाएं और इसे एक टेक्स्ट फ़ाइल में सहेजें।

#### प्रश्न: निकाली गई लाइन ब्रेक जानकारी का उद्देश्य क्या है?

उ: निकाली गई लाइन ब्रेक जानकारी पीडीएफ दस्तावेज़ में मौजूद लाइन ब्रेक और सूचनाओं के बारे में विवरण प्रदान करती है। यह विश्लेषण करने और समझने के लिए उपयोगी हो सकता है कि दस्तावेज़ के भीतर पाठ और पैराग्राफ कैसे संरचित हैं।

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में लाइन ब्रेक कैसे निर्धारित किया जाए। आप इस ज्ञान का उपयोग प्रोग्रामेटिक रूप से पीडीएफ फाइलों से लाइन ब्रेक जानकारी निकालने और उसका विश्लेषण करने के लिए कर सकते हैं।