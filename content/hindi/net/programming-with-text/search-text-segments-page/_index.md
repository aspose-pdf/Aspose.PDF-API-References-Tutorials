---
title: पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें
linktitle: पीडीएफ फाइल में टेक्स्ट सेगमेंट पेज खोजें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस विस्तृत चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइलों में टेक्स्ट सेगमेंट खोजना सीखें। टेक्स्ट निकालें, सेगमेंट का विश्लेषण करें, और बहुत कुछ।
type: docs
weight: 470
url: /hi/net/programming-with-text/search-text-segments-page/
---
## परिचय

कभी सोचा है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में विशिष्ट टेक्स्ट सेगमेंट कैसे ढूँढ़ें? खैर, आप किस्मतवाले हैं! इस गाइड में, हम आपको एक सरल, चरण-दर-चरण प्रारूप में प्रक्रिया से गुज़रने जा रहे हैं। चाहे आप जानकारी निकालने, टेक्स्ट का विश्लेषण करने या बस PDF हेरफेर की पेचीदगियों को नेविगेट करने का प्रयास कर रहे हों, .NET के लिए Aspose.PDF आपके लिए है। आइए शुरू करते हैं!

## आवश्यक शर्तें

शुरू करने से पहले, आइए सुनिश्चित करें कि आपके पास वह सब कुछ है जो आपको चाहिए:

-  .NET के लिए Aspose.PDF: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। आप इसे यहाँ से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/net/).
- .NET फ्रेमवर्क: सुनिश्चित करें कि आपकी मशीन पर .NET स्थापित है।
- विकास वातावरण: विज़ुअल स्टूडियो या कोई भी .NET समर्थित IDE अनुशंसित है।
- पीडीएफ दस्तावेज़: एक पीडीएफ फाइल जहां आप पाठ खंडों की खोज करेंगे।

 यदि आपके पास अभी तक .NET के लिए Aspose.PDF नहीं है, तो चिंता न करें! आप यहाँ से निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/) या इसे खरीदें[यहाँ](https://purchase.aspose.com/buy).

## पैकेज आयात करें

कोडिंग शुरू करने से पहले, आपके प्रोजेक्ट में आवश्यक पैकेज आयात करना महत्वपूर्ण है। यह सुनिश्चित करता है कि आपके PDF मैनिपुलेशन कार्यों के लिए सभी आवश्यक क्लास और विधियाँ उपलब्ध हैं।

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

आवश्यक बातें जान लेने के बाद, आइए सीधे चरण-दर-चरण मार्गदर्शिका पर चलते हैं।


## चरण 1: पीडीएफ दस्तावेज़ लोड करें

इस प्रक्रिया का पहला चरण आपकी PDF फ़ाइल को प्रोग्राम में लोड करना है। लोड किए गए दस्तावेज़ के बिना, खोजने के लिए कुछ भी नहीं है, है न? यहाँ बताया गया है कि आप इसे कैसे करते हैं।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` : यह वेरिएबल आपकी PDF फ़ाइल का पथ रखता है।`"YOUR DOCUMENT DIRECTORY"` वास्तविक निर्देशिका के साथ जहां आपकी फ़ाइल संग्रहीत है.
- `pdfDocument` : का उपयोग`Document` क्लास में, हम पीडीएफ को मेमोरी में लोड करते हैं।

## चरण 2: टेक्स्ट खोज सेट करें

 अब जब आपका दस्तावेज़ लोड हो गया है, तो अगला चरण एक दस्तावेज़ बनाना है।`TextFragmentAbsorber` ऑब्जेक्ट, जो हमें दस्तावेज़ के भीतर विशिष्ट पाठ की खोज करने की अनुमति देता है।

```csharp
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएँ
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` : इस ऑब्जेक्ट का उपयोग आपके द्वारा खोजे जा रहे टेक्स्ट की सभी घटनाओं को कैप्चर करने के लिए किया जाता है।`"text"` उस वास्तविक पाठ के साथ जिसे आप खोजना चाहते हैं.

## चरण 3: विशिष्ट पृष्ठ(ओं) के लिए अवशोषक को स्वीकार करें

हो सकता है कि आप हमेशा संपूर्ण PDF दस्तावेज़ को खोजना न चाहें। इस उदाहरण में, हम इसे एक विशिष्ट पृष्ठ तक सीमित कर रहे हैं।

```csharp
// सभी पृष्ठों के लिए अवशोषक स्वीकार करें
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: यह दर्शाता है कि हम दस्तावेज़ के केवल दूसरे पृष्ठ को खोज रहे हैं। आप अन्य पृष्ठों को लक्षित करने के लिए इंडेक्स को संशोधित कर सकते हैं।
- `Accept()` : यह विधि अनुमति देती है`TextFragmentAbsorber` निर्दिष्ट पृष्ठ के भीतर पाठ को संसाधित करने के लिए.

## चरण 4: पाठ अंश निकालें

पृष्ठ पर खोज करने के बाद, हम पाए गए पाठ अंशों को एक संग्रह में निकालते हैं।

```csharp
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`: यह संग्रह खोज प्रक्रिया के दौरान पाए गए पाठ अंशों के सभी उदाहरण रखता है।

## चरण 5: पाठ अंशों के माध्यम से लूप करें और डेटा निकालें

अब, आइए प्रत्येक पाठ खंड को लूप करें और उसके विवरण निकालें, जैसे कि स्थिति, फ़ॉन्ट और रंग।

```csharp
// टुकड़ों के माध्यम से लूप
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)` : हम प्रत्येक के माध्यम से लूप करते हैं`TextFragment` संग्रह में.
- `foreach (TextSegment textSegment in textFragment.Segments)`: प्रत्येक खंड के अंदर कई खंड होते हैं। हम सभी प्रासंगिक जानकारी एकत्र करने के लिए उनके माध्यम से लूप करते हैं।
-  के विभिन्न गुण`textSegment`ये हमें पाठ के बारे में विस्तृत जानकारी देते हैं, जैसे कि इसकी स्थिति (X और Y), फ़ॉन्ट विवरण, आकार और रंग।

## चरण 6: परिणाम आउटपुट करें

अंत में, सारी जानकारी निकालने के बाद, परिणाम कंसोल में प्रिंट किए जाते हैं। इससे आपको यह देखने में मदद मिलती है कि टेक्स्ट कहाँ स्थित है और उसका फ़ॉर्मेटिंग विवरण क्या है।

स्पष्टता के लिए यहां एक नमूना आउटपुट दिया गया है:

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- यह आउटपुट आपको निर्दिष्ट पृष्ठ पर पाठ "text" का सटीक स्थान और स्वरूपण जानकारी देता है।

## निष्कर्ष

और अब यह हो गया! आपने अभी सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में विशिष्ट टेक्स्ट खंडों को कैसे खोजना है। बड़े PDF से निपटने के दौरान यह प्रक्रिया बहुत उपयोगी है, जिससे आप मुख्य टेक्स्ट को कुशलतापूर्वक पहचान और निकाल सकते हैं। चाहे डेटा का विश्लेषण करना हो, जानकारी निकालना हो, या किसी दस्तावेज़ में नेविगेट करना हो, Aspose.PDF आपको काम पूरा करने के लिए शक्तिशाली उपकरण प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं एकाधिक शब्दों या वाक्यांशों की खोज कर सकता हूँ?
 हां, आप इसे संशोधित कर सकते हैं`TextFragmentAbsorber`इनपुट स्ट्रिंग को बदलकर भिन्न पाठ खोजने के लिए।

### क्या एकाधिक पृष्ठों पर खोज करना संभव है?
 बिलकुल! आप पीडीएफ में सभी पृष्ठों को दोहराकर लूप कर सकते हैं`pdfDocument.Pages`.

### मैं केस-इनसेंसिटिव टेक्स्ट कैसे खोजूं?
 आप उपयोग कर सकते हैं`TextSearchOptions` केस-असंवेदनशील खोज को सक्षम करने के लिए।

### क्या मैं पाठ ढूंढने के बाद उसे संशोधित कर सकता हूं?
 हाँ, एक बार जब आप एक का पता लगा लेते हैं`TextFragment`, आप इसके पाठ गुणों को संशोधित कर सकते हैं.

### क्या यह विधि एन्क्रिप्टेड पीडीएफ पर लागू है?
हां, बशर्ते आप सही पासवर्ड का उपयोग करके पीडीएफ को अनलॉक करें।