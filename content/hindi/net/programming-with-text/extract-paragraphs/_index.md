---
title: पैराग्राफ को पीडीएफ फाइल में निकालें
linktitle: पैराग्राफ को पीडीएफ फाइल में निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पैराग्राफ़ निकालने का तरीका जानें।
type: docs
weight: 160
url: /hi/net/programming-with-text/extract-paragraphs/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पैराग्राफ़ निकालने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ से आप पैराग्राफ़ निकालना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: पीडीएफ दस्तावेज़ खोलें
 किसी मौजूदा PDF दस्तावेज़ को खोलने के लिए निम्न का उपयोग करें:`Document` कन्स्ट्रक्टर का उपयोग करना और इनपुट पीडीएफ फाइल का पथ पास करना।

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## चरण 5: पैराग्राफ़ निकालें
 उदाहरण प्रस्तुत करें`ParagraphAbsorber` क्लास और इसका उपयोग करें`Visit` दस्तावेज़ से पैराग्राफ़ निकालने की विधि.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## चरण 6: पैराग्राफ़ों को दोहराएँ
निकाले गए पैराग्राफ़ में लूप करके टेक्स्ट कंटेंट तक पहुँचें। प्रत्येक पैराग्राफ़ के अंदर सेक्शन और लाइनों में जाने के लिए नेस्टेड लूप का इस्तेमाल करें।

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

### .NET के लिए Aspose.PDF का उपयोग करके पैराग्राफ़ निकालने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// मौजूदा PDF फ़ाइल खोलें
Document doc = new Document(dataDir + "input.pdf");
// पैराग्राफ अवशोषक को तत्कालित करें
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
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से पैराग्राफ़ सफलतापूर्वक निकाले हैं। निकाले गए पैराग्राफ़ कंसोल विंडो में प्रदर्शित किए गए हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल से पैराग्राफ़ निकालने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। साथ में दिया गया C# स्रोत कोड इस कार्य को पूरा करने के लिए व्यावहारिक कदम प्रदान करता है।

#### प्रश्न: मुझे कौन से नामस्थान आयात करने चाहिए?

उत्तर: जिस कोड फ़ाइल से आप पैराग्राफ़ निकालना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित using निर्देश शामिल करें:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` कोड में और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं किसी मौजूदा पीडीएफ दस्तावेज़ को कैसे खोलूं?

 उत्तर: चरण 4 में, आप एक मौजूदा पीडीएफ दस्तावेज़ को खोलेंगे`Document` कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ प्रदान करना।

#### प्रश्न: मैं दस्तावेज़ से पैराग्राफ़ कैसे निकालूँ?

 उत्तर: चरण 5 में एक उदाहरण बनाना शामिल है`ParagraphAbsorber` कक्षा और उसके उपयोग से`Visit` पीडीएफ दस्तावेज़ से पैराग्राफ़ निकालने की विधि।

#### प्रश्न: मैं निकाले गए पैराग्राफों को कैसे दोहराऊं?

उत्तर: चरण 6 आपको निकाले गए पैराग्राफ़ के माध्यम से लूपिंग के माध्यम से मार्गदर्शन करता है। नेस्टेड लूप का उपयोग प्रत्येक पैराग्राफ़ के भीतर अनुभागों और पंक्तियों को पार करने के लिए किया जाता है, अंततः पाठ सामग्री तक पहुँचने और प्रदर्शित करने के लिए।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से पैराग्राफ़ कैसे निकालें। निकाले गए पैराग्राफ़ कंसोल विंडो में प्रदर्शित किए गए हैं, जो आपको दस्तावेज़ की सामग्री संरचना में मूल्यवान जानकारी प्रदान करते हैं।