---
title: पीडीएफ फाइल में पैराग्राफ निकालें
linktitle: पीडीएफ फाइल में पैराग्राफ निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पैराग्राफ निकालने का तरीका जानें।
type: docs
weight: 160
url: /hi/net/programming-with-text/extract-paragraphs/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में पैराग्राफ निकालने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप पैराग्राफ निकालना चाहते हैं, फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: पीडीएफ दस्तावेज़ खोलें
 का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ खोलें`Document`कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ पास करना।

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## चरण 5: पैराग्राफ निकालें
 त्वरित करें`ParagraphAbsorber` कक्षा और इसका उपयोग करें`Visit` दस्तावेज़ से अनुच्छेद निकालने की विधि.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## चरण 6: अनुच्छेदों के माध्यम से पुनरावृति करें
पाठ्य सामग्री तक पहुँचने के लिए निकाले गए अनुच्छेदों के माध्यम से लूप करें। प्रत्येक पैराग्राफ के भीतर अनुभागों और रेखाओं को पार करने के लिए नेस्टेड लूप का उपयोग करें।

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### .NET के लिए Aspose.PDF का उपयोग करके पैराग्राफ निकालने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//एक मौजूदा पीडीएफ फाइल खोलें
Document doc = new Document(dataDir + "input.pdf");
// पैराग्राफअवशोषक को त्वरित करें
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से पैराग्राफ सफलतापूर्वक निकाल लिया है। निकाले गए पैराग्राफ कंसोल विंडो में प्रदर्शित किए गए हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फ़ाइल से पैराग्राफ निकालने की प्रक्रिया में आपका मार्गदर्शन करना है। संलग्न C# स्रोत कोड इस कार्य को प्राप्त करने के लिए व्यावहारिक कदम प्रदान करता है।

#### प्रश्न: मुझे कौन से नामस्थान आयात करने चाहिए?

उ: कोड फ़ाइल में जहां आप पैराग्राफ निकालना चाहते हैं, फ़ाइल की शुरुआत में निर्देशों का उपयोग करते हुए निम्नलिखित शामिल करें:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` कोड में और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं मौजूदा पीडीएफ दस्तावेज़ कैसे खोलूं?

 उ: चरण 4 में, आप इसका उपयोग करके एक मौजूदा पीडीएफ दस्तावेज़ खोलेंगे`Document` कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ प्रदान करना।

#### प्रश्न: मैं दस्तावेज़ से पैराग्राफ कैसे निकालूं?

 उ: चरण 5 में इसका एक उदाहरण बनाना शामिल है`ParagraphAbsorber` कक्षा और इसका उपयोग करना`Visit` पीडीएफ दस्तावेज़ से पैराग्राफ निकालने की विधि।

#### प्रश्न: मैं निकाले गए अनुच्छेदों को कैसे दोहराऊं?

उ: चरण 6 आपको निकाले गए अनुच्छेदों के माध्यम से लूपिंग के माध्यम से मार्गदर्शन करता है। नेस्टेड लूप्स का उपयोग प्रत्येक पैराग्राफ के भीतर अनुभागों और रेखाओं को पार करने, अंततः पाठ सामग्री तक पहुंचने और प्रदर्शित करने के लिए किया जाता है।

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ से पैराग्राफ कैसे निकाले जाते हैं। निकाले गए पैराग्राफ कंसोल विंडो में प्रदर्शित किए गए हैं, जो आपको दस्तावेज़ की सामग्री संरचना में मूल्यवान जानकारी प्रदान करते हैं।