---
title: पीडीएफ फाइल में लाइन ब्रेक निर्धारित करें
linktitle: पीडीएफ फाइल में लाइन ब्रेक निर्धारित करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में लाइन ब्रेक निर्धारित करना सीखें।
type: docs
weight: 130
url: /hi/net/programming-with-text/determine-line-break/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में लाइन ब्रेक निर्धारित करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को प्रदर्शित करता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप लाइन ब्रेक निर्धारित करना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using System.IO;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: एक नया दस्तावेज़ इंस्टेंस बनाएँ
 एक नया उदाहरण बनाएँ`Document` निम्न कोड पंक्ति जोड़कर ऑब्जेक्ट बनाएँ:

```csharp
Document doc = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages` संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`page`.

```csharp
Page page = doc.Pages.Add();
```

## चरण 6: लाइन ब्रेक के साथ टेक्स्ट अंश जोड़ें
पृष्ठ पर एकाधिक पाठ खंड जोड़ने के लिए एक लूप बनाएं, जिनमें से प्रत्येक में पंक्ति विराम के साथ एक पैराग्राफ हो।

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## चरण 7: पीडीएफ दस्तावेज़ को सहेजें और लाइन ब्रेक जानकारी निकालें
 पीडीएफ दस्तावेज़ को सेव करने के लिए निम्न का उपयोग करें:`Save` की विधि`Document` ऑब्जेक्ट। फिर, लाइन ब्रेक जानकारी का उपयोग करके निकालें`GetNotifications` वांछित पृष्ठ की विधि.

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
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में लाइन ब्रेक सफलतापूर्वक निर्धारित कर लिया है। लाइन ब्रेक जानकारी निकाल ली गई है और उसे टेक्स्ट फ़ाइल में सहेज लिया गया है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का मुख्य फोकस क्या है?

उत्तर: यह ट्यूटोरियल आपको .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में लाइन ब्रेक निर्धारित करने की प्रक्रिया के माध्यम से मार्गदर्शन करने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने चाहिए?

उत्तर: कोड फ़ाइल में जहाँ आप लाइन ब्रेक निर्धारित करना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उत्तर: चरण 4 में, आप एक नया इन्स्टेन्सिएट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट को चिह्नित करें।

#### प्रश्न: मैं दस्तावेज़ में पृष्ठ कैसे जोड़ूं?

 उत्तर: चरण 5 में, आप दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं लाइन ब्रेक के साथ पाठ अंश कैसे जोड़ूं?

उत्तर: चरण 6 में, आप पृष्ठ पर एकाधिक पाठ अंश जोड़ने के लिए एक लूप बनाएंगे, जिनमें से प्रत्येक में पंक्ति विराम के साथ एक पैराग्राफ होगा।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को कैसे सहेजूँ और लाइन ब्रेक जानकारी कैसे निकालूँ?

 उत्तर: चरण 7 में, आप PDF दस्तावेज़ को निम्न का उपयोग करके सहेजेंगे:`Save` की विधि`Document` ऑब्जेक्ट। फिर, आप लाइन ब्रेक जानकारी का उपयोग करके निकालेंगे`GetNotifications` वांछित पृष्ठ की विधि का चयन करें और उसे एक टेक्स्ट फ़ाइल में सहेजें।

#### प्रश्न: निकाली गई लाइन ब्रेक जानकारी का उद्देश्य क्या है?

उत्तर: निकाली गई लाइन ब्रेक जानकारी पीडीएफ दस्तावेज़ में मौजूद लाइन ब्रेक और सूचनाओं के बारे में विवरण प्रदान करती है। यह विश्लेषण करने और यह समझने के लिए उपयोगी हो सकता है कि दस्तावेज़ के भीतर पाठ और पैराग्राफ़ कैसे संरचित हैं।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में लाइन ब्रेक कैसे निर्धारित करें। आप इस ज्ञान का उपयोग प्रोग्रामेटिक रूप से PDF फ़ाइलों से लाइन ब्रेक जानकारी निकालने और उसका विश्लेषण करने के लिए कर सकते हैं।