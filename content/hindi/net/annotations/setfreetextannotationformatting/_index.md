---
title: निःशुल्क टेक्स्ट एनोटेशन फ़ॉर्मेटिंग सेट करें
linktitle: निःशुल्क टेक्स्ट एनोटेशन फ़ॉर्मेटिंग सेट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: यह आलेख एक निःशुल्क टेक्स्ट एनोटेशन बनाने और .NET के लिए Aspose.PDF का उपयोग करके इसकी सामग्री निर्दिष्ट करने के बारे में चरण-दर-चरण मार्गदर्शिका प्रदान करता है।
type: docs
weight: 140
url: /hi/net/annotations/setfreetextannotationformatting/
---
.NET के लिए Aspose.PDF एक शक्तिशाली और उपयोग में आसान पीडीएफ दस्तावेज़ हेरफेर एपीआई है जो आपको अपने .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से पीडीएफ फाइलों के साथ काम करने की अनुमति देता है। .NET के लिए Aspose.PDF द्वारा प्रदान की गई सुविधाओं में से एक पीडीएफ दस्तावेजों में मुफ्त टेक्स्ट एनोटेशन फ़ॉर्मेटिंग सेट करने की क्षमता है। इस लेख में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके निःशुल्क टेक्स्ट एनोटेशन फ़ॉर्मेटिंग सेट करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- माइक्रोसॉफ्ट विज़ुअल स्टूडियो 2010 या बाद का संस्करण
- .NET के लिए Aspose.PDF
- सी# का बुनियादी ज्ञान



## चरण 1: एक नया C# कंसोल एप्लिकेशन बनाएं

सबसे पहले, Microsoft Visual Studio में एक नया C# कंसोल एप्लिकेशन बनाएं। नया कंसोल एप्लिकेशन बनाने के लिए, मुख्य मेनू से "फ़ाइल" > "नया" > "प्रोजेक्ट" > "विज़ुअल सी#" > "कंसोल एप्लिकेशन" चुनें।

## चरण 2: .NET के लिए Aspose.PDF का संदर्भ जोड़ें

इसके बाद, अपने प्रोजेक्ट में .NET के लिए Aspose.PDF का एक संदर्भ जोड़ें। ऐसा करने के लिए, "समाधान एक्सप्लोरर" फलक में अपने प्रोजेक्ट पर राइट-क्लिक करें, "जोड़ें" > "संदर्भ" चुनें, और फिर उस स्थान पर ब्राउज़ करें जहां आपने .NET DLL फ़ाइल के लिए Aspose.PDF को सहेजा था। DLL फ़ाइल का चयन करें और अपने प्रोजेक्ट में संदर्भ जोड़ने के लिए "ओके" पर क्लिक करें।

## चरण 3: वातावरण स्थापित करें

.NET के लिए Aspose.PDF का संदर्भ जोड़ने के बाद, आपको पर्यावरण स्थापित करने की आवश्यकता है। ऐसा करने के लिए, "डेटाडिर" नामक एक नया स्ट्रिंग वैरिएबल बनाएं और इसे उस निर्देशिका के पथ पर सेट करें जहां आपका पीडीएफ दस्तावेज़ स्थित है। नीचे दिए गए कोड में "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 4: पीडीएफ दस्तावेज़ खोलें

एक बार जब आप वातावरण स्थापित कर लेते हैं, तो आप निम्नलिखित कोड का उपयोग करके पीडीएफ दस्तावेज़ खोल सकते हैं:

```csharp
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

"SetFreeTextAnnotationFormatting.pdf" को अपने पीडीएफ दस्तावेज़ के वास्तविक नाम से बदलें।

## चरण 5: डिफ़ॉल्ट उपस्थिति सेट करें

मुफ़्त टेक्स्ट एनोटेशन के डिफ़ॉल्ट स्वरूप को सेट करने के लिए, आपको वांछित फ़ॉन्ट, फ़ॉन्ट आकार और रंग के साथ DefaultAppearance ऑब्जेक्ट को तुरंत चालू करना होगा। इस ट्यूटोरियल में, हम फ़ॉन्ट को "एरियल", फ़ॉन्ट का आकार 28 और रंग को लाल पर सेट कर रहे हैं।

```csharp
// DefaultAppearance ऑब्जेक्ट को त्वरित करें
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## चरण 6: एक निःशुल्क टेक्स्ट एनोटेशन बनाएं

अब जब आपने डिफ़ॉल्ट स्वरूप सेट कर लिया है, तो आप निम्नलिखित कोड का उपयोग करके एक निःशुल्क टेक्स्ट एनोटेशन बना सकते हैं:

```csharp
// एनोटेशन बनाएं
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

उपरोक्त कोड पीडीएफ दस्तावेज़ के दूसरे पृष्ठ पर एक नया मुफ़्त टेक्स्ट एनोटेशन बनाता है। एनोटेशन (200, 400) पर स्थित होगा और इसकी चौड़ाई 400 और ऊंचाई 600 होगी।

## चरण 7: एनोटेशन की सामग्री निर्दिष्ट करें

निःशुल्क टेक्स्ट एनोटेशन बनाने के बाद, आप निम्नलिखित कोड का उपयोग करके एनोटेशन की सामग्री निर्दिष्ट कर सकते हैं:

```csharp
// एनोटेशन की सामग्री निर्दिष्ट करें
freetext.Contents = "Free Text
```

### .NET के लिए Aspose.PDF का उपयोग करके सेट फ्री टेक्स्ट एनोटेशन फ़ॉर्मेटिंग के लिए उदाहरण स्रोत कोड
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// DefaultAppearance ऑब्जेक्ट को त्वरित करें
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// एनोटेशन बनाएं
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// एनोटेशन की सामग्री निर्दिष्ट करें
freetext.Contents = "Free Text";
// पृष्ठ के एनोटेशन संग्रह में एनोटेशन जोड़ें
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// अद्यतन दस्तावेज़ सहेजें
pdfDocument.Save(dataDir);            
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में मुफ्त टेक्स्ट एनोटेशन फ़ॉर्मेटिंग कैसे सेट करें। लाइब्रेरी पीडीएफ दस्तावेजों के साथ प्रोग्रामेटिक रूप से काम करने का एक सीधा और कुशल तरीका प्रदान करती है, जिससे डेवलपर्स को मुफ्त टेक्स्ट एनोटेशन सहित विभिन्न प्रकार के एनोटेशन बनाने और अनुकूलित करने की अनुमति मिलती है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप आसानी से वातावरण सेट कर सकते हैं, एक पीडीएफ दस्तावेज़ खोल सकते हैं, और कस्टम फ़ॉर्मेटिंग के साथ एक निःशुल्क टेक्स्ट एनोटेशन बना सकते हैं। .NET के लिए Aspose.PDF एक मजबूत और विश्वसनीय एपीआई है जो पीडीएफ दस्तावेज़ हेरफेर कार्यों को सरल बनाता है, जिससे यह पीडीएफ फाइलों के साथ काम करने वाले .NET डेवलपर्स के लिए एक मूल्यवान उपकरण बन जाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में मुफ़्त टेक्स्ट एनोटेशन क्या है?

उ: पीडीएफ दस्तावेज़ में एक निःशुल्क टेक्स्ट एनोटेशन एक प्रकार का एनोटेशन है जो आपको किसी विशिष्ट स्थान या संरचना से बंधे बिना दस्तावेज़ में टेक्स्ट जोड़ने की अनुमति देता है। इसका उपयोग आमतौर पर दस्तावेज़ में टिप्पणियाँ, नोट्स या अन्य अतिरिक्त जानकारी प्रदान करने के लिए किया जाता है।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके निःशुल्क टेक्स्ट एनोटेशन की उपस्थिति को अनुकूलित कर सकता हूँ?

उत्तर: हां, आप मुफ़्त टेक्स्ट एनोटेशन के विभिन्न गुणों को अनुकूलित कर सकते हैं, जैसे कि फ़ॉन्ट, फ़ॉन्ट आकार, रंग, स्थिति और बहुत कुछ।

#### प्रश्न: मैं निःशुल्क टेक्स्ट एनोटेशन की सामग्री कैसे निर्दिष्ट करूं?

 उ: निःशुल्क टेक्स्ट एनोटेशन की सामग्री निर्दिष्ट करने के लिए, आप सेट कर सकते हैं`Contents` की संपत्ति`FreeTextAnnotation` वांछित पाठ पर आपत्ति.

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में एकाधिक निःशुल्क टेक्स्ट एनोटेशन जोड़ सकता हूँ?

 उ: हां, आप एक पीडीएफ दस्तावेज़ में कई उदाहरण बनाकर कई मुफ्त टेक्स्ट एनोटेशन बना सकते हैं`FreeTextAnnotation`ऑब्जेक्ट करना और उन्हें दस्तावेज़ में विभिन्न पृष्ठों या स्थानों पर जोड़ना।