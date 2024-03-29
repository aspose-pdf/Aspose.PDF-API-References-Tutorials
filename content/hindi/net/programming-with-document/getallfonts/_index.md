---
title: सभी फ़ॉन्ट्स पीडीएफ फाइल में प्राप्त करें
linktitle: सभी फ़ॉन्ट्स पीडीएफ फाइल में प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका और उदाहरण कोड के साथ पीडीएफ फ़ाइल में उपयोग किए गए सभी फ़ॉन्ट्स को प्रोग्रामेटिक रूप से प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग करना सीखें।
type: docs
weight: 160
url: /hi/net/programming-with-document/getallfonts/
---
.NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PDF फ़ाइल के साथ काम करने में सक्षम बनाती है। इसके द्वारा प्रदान की जाने वाली सुविधाओं में से एक पीडीएफ फ़ाइल में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करने की क्षमता है। यह उपयोगी हो सकता है यदि आपको पीडीएफ फ़ाइल में फ़ॉन्ट्स का प्रोग्रामेटिक रूप से विश्लेषण या हेरफेर करने की आवश्यकता है।

इस ट्यूटोरियल में, हम चर्चा करेंगे कि PDF दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। हम उदाहरण स्रोत कोड के साथ, इसे कैसे करें, इस पर चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे।

## चरण 1: एक नया C# कंसोल एप्लिकेशन बनाएं
आरंभ करने के लिए, विज़ुअल स्टूडियो में एक नया C# कंसोल एप्लिकेशन बनाएं। आप इसे जो चाहें नाम दे सकते हैं। एक बार प्रोजेक्ट बन जाने के बाद, आपको .NET लाइब्रेरी के लिए Aspose.PDF में एक संदर्भ जोड़ना होगा।

## चरण 2: Aspose.PDF नेमस्पेस आयात करें
Aspose.PDF नेमस्पेस को आयात करने के लिए अपनी C# फ़ाइल के शीर्ष पर कोड की निम्नलिखित पंक्ति जोड़ें:

```csharp
using Aspose.Pdf;
```

## चरण 3: पीडीएफ दस्तावेज़ लोड करें
वह पीडीएफ दस्तावेज़ लोड करें जिससे आप फ़ॉन्ट प्राप्त करना चाहते हैं:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## चरण 4: सभी फ़ॉन्ट प्राप्त करें
पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करें:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## चरण 5: सभी फ़ॉन्ट प्रिंट करें
पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्रिंट करें:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### .NET के लिए Aspose.PDF का उपयोग करके सभी फ़ॉन्ट प्राप्त करने के लिए उदाहरण स्रोत कोड
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने चर्चा की है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट कैसे प्राप्त करें। यदि आपको पीडीएफ दस्तावेज़ में फ़ॉन्ट्स का प्रोग्रामेटिक रूप से विश्लेषण या हेरफेर करने की आवश्यकता है, तो पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करना उपयोगी हो सकता है। .NET के लिए Aspose.PDF, PDF दस्तावेज़ों के साथ काम करने के लिए एक सरल और उपयोग में आसान एपीआई प्रदान करता है, जिसमें एक पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करना शामिल है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मुझे पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करने की आवश्यकता क्यों होगी?

उ: यदि आपको फ़ॉन्ट प्रतिस्थापन या फ़ॉन्ट अनुकूलन जैसे विभिन्न उद्देश्यों के लिए फ़ॉन्ट का प्रोग्रामेटिक रूप से विश्लेषण या हेरफेर करने की आवश्यकता है, तो पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त करना उपयोगी हो सकता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट कैसे प्राप्त कर सकता हूं?

 उ: आप कॉल करके .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में उपयोग किए गए सभी फ़ॉन्ट प्राप्त कर सकते हैं`GetAllFonts` की विधि`FontUtilities` कक्षा। यह विधि एक सरणी लौटाती है`Aspose.Pdf.Text.Font` ऑब्जेक्ट, जो पीडीएफ दस्तावेज़ में उपयोग किए गए फ़ॉन्ट का प्रतिनिधित्व करते हैं।

#### प्रश्न: क्या मैं कुछ मानदंडों के आधार पर फ़ॉन्ट फ़िल्टर कर सकता हूँ?

उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके कुछ मानदंडों के आधार पर फ़ॉन्ट फ़िल्टर कर सकते हैं। सभी फ़ॉन्ट प्राप्त करने के बाद, आप प्रोग्रामेटिक रूप से फ़ॉन्ट का विश्लेषण कर सकते हैं और आवश्यकतानुसार फ़िल्टरिंग तर्क लागू कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF विभिन्न फ़ॉन्ट प्रारूपों के साथ संगत है?

उत्तर: हाँ, .NET के लिए Aspose.PDF ट्रू टाइप, ओपन टाइप और टाइप 1 फ़ॉन्ट सहित विभिन्न फ़ॉन्ट प्रारूपों के साथ संगत है। यह विभिन्न फ़ॉन्ट प्रारूपों के साथ काम कर सकता है और पीडीएफ दस्तावेज़ हेरफेर के दौरान उन्हें संभाल सकता है।