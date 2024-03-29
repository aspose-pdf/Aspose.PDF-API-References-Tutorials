---
title: जावा का उपयोग करके पीडीएफ में घुमाया गया टेक्स्ट जोड़ें
linktitle: जावा का उपयोग करके पीडीएफ में घुमाया गया टेक्स्ट जोड़ें
second_title: Aspose.PDF जावा पीडीएफ प्रोसेसिंग एपीआई
description: जावा का उपयोग करके पीडीएफ दस्तावेज़ में घुमाए गए टेक्स्ट को सम्मिलित करना सीखें। घुमाए गए टेक्स्ट के साथ अपने पीडीएफ को बेहतर बनाने के लिए कोड उदाहरणों के साथ इस विस्तृत चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 14
url: /hi/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## परिचय

इस व्यापक ट्यूटोरियल में, हम जावा का उपयोग करके पीडीएफ दस्तावेज़ में घुमाए गए टेक्स्ट को जोड़ने की प्रक्रिया के बारे में विस्तार से जानेंगे। चाहे आपको आरेखों को लेबल करने, वॉटरमार्क बनाने, या अपने पीडीएफ़ में विशेष प्रभाव जोड़ने की आवश्यकता हो, यह मार्गदर्शिका आपको सभी चरणों के बारे में बताएगी। हम प्रक्रिया को प्रदर्शित करने के लिए जावा के लिए Aspose.PDF का उपयोग करेंगे, जो PDF हेरफेर के लिए एक शक्तिशाली लाइब्रेरी है।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।

2.  जावा के लिए Aspose.PDF: Aspose.PDF लाइब्रेरी को डाउनलोड करें और अपने जावा प्रोजेक्ट में शामिल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/pdf/java/).

## चरण 1: एक नया पीडीएफ दस्तावेज़ बनाएं

आइए Aspose.PDF का उपयोग करके एक नया PDF दस्तावेज़ बनाकर शुरुआत करें। यह दस्तावेज़ हमारे घुमाए गए पाठ के लिए कैनवास के रूप में काम करेगा।

```java
// पीडीएफ दस्तावेज़ को प्रारंभ करें
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## चरण 2: एक पेज जोड़ें

इसके बाद, पीडीएफ दस्तावेज़ में एक पेज जोड़ें जहां आप घुमाया गया टेक्स्ट डालना चाहते हैं:

```java
//दस्तावेज़ में एक नया पृष्ठ जोड़ें
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## चरण 3: घुमाए गए पाठ को परिभाषित करें

अब, आइए उस टेक्स्ट को परिभाषित करें जिसे आप सम्मिलित करना और घुमाना चाहते हैं। आप अपनी आवश्यकताओं के अनुसार टेक्स्ट, फ़ॉन्ट और रोटेशन कोण को अनुकूलित कर सकते हैं:

```java
// पाठ्य सामग्री को परिभाषित करें
String text = "Rotated Text Example";

// एक टेक्स्टफ्रैगमेंट ऑब्जेक्ट बनाएं
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// फ़ॉन्ट आकार और शैली सेट करें
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// घूर्णन कोण को परिभाषित करें (डिग्री में)
textFragment.setTextRotation(45);
```

इस उदाहरण में, हमने टेक्स्ट को "रोटेटेड टेक्स्ट उदाहरण" पर सेट किया है, एरियल फ़ॉन्ट चुना है, फ़ॉन्ट का आकार 12 पर सेट किया है, और टेक्स्ट को 45 डिग्री तक घुमाया है। अपनी विशिष्ट आवश्यकताओं से मेल खाने के लिए इन मापदंडों को समायोजित करें।

## चरण 4: घुमाए गए टेक्स्ट को स्थिति में रखें

पृष्ठ पर वह स्थान निर्दिष्ट करें जहाँ आप घुमाए गए पाठ को रखना चाहते हैं:

```java
// पाठ की स्थिति निर्धारित करें
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

यहां, हमने पृष्ठ पर पाठ को निर्देशांक (100, 200) पर रखा है। पाठ को ठीक वहीं रखने के लिए इन निर्देशांकों को संशोधित करें जहां आपको इसकी आवश्यकता है।

## चरण 5: पृष्ठ पर घुमाया गया टेक्स्ट जोड़ें

अब, घुमाए गए टेक्स्ट को पेज पर जोड़ें:

```java
// घुमाए गए टेक्स्ट को पेज पर जोड़ें
page.getParagraphs().add(textFragment);
```

## चरण 6: पीडीएफ को सेव करें

अंत में, पीडीएफ दस्तावेज़ को घुमाए गए टेक्स्ट के साथ सहेजें:

```java
// पीडीएफ दस्तावेज़ सहेजें
pdfDocument.save("output.pdf");
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा और जावा के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में घुमाए गए टेक्स्ट को जोड़ने की प्रक्रिया का पता लगाया है। आपने सीखा है कि एक नया पीडीएफ कैसे बनाएं, कस्टम शैलियों के साथ घुमाए गए टेक्स्ट को कैसे परिभाषित करें, इसे पृष्ठ पर कैसे रखें, और संशोधित पीडीएफ को कैसे सहेजें।

घुमाया गया टेक्स्ट विभिन्न उद्देश्यों के लिए आपके पीडीएफ में एक मूल्यवान अतिरिक्त हो सकता है, जैसे कि आरेखों को लेबल करना, वॉटरमार्किंग करना, या आपके दस्तावेज़ों में रचनात्मक तत्व जोड़ना।

जावा के लिए Aspose.PDF की क्षमताओं की बदौलत, आसानी से घुमाए गए टेक्स्ट को शामिल करके अपने पीडीएफ दस्तावेज़ों को बेहतर बनाएं।

---

## अक्सर पूछे जाने वाले प्रश्न (अक्सर पूछे जाने वाले प्रश्न)

### 1. क्या मैं एक ही पीडीएफ में टेक्स्ट को विभिन्न कोणों से घुमा सकता हूँ?
   हां, आप एक ही पीडीएफ दस्तावेज़ में अलग-अलग कोणों से घुमाए गए टेक्स्ट के कई उदाहरण जोड़ सकते हैं। घुमाए गए पाठ के प्रत्येक टुकड़े के लिए बस इस ट्यूटोरियल में वर्णित प्रक्रिया को दोहराएं।

### 2. मैं घुमाए गए टेक्स्ट का रंग कैसे बदल सकता हूँ?
    टेक्स्ट का रंग बदलने के लिए, का उपयोग करें`textFragment.getTextState().setForegroundColor` विधि और आरजीबी प्रारूप में रंग निर्दिष्ट करें। उदाहरण के लिए, टेक्स्ट का रंग लाल पर सेट करने के लिए, उपयोग करें`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. क्या जावा के लिए Aspose.PDF एक निःशुल्क लाइब्रेरी है?
   जावा के लिए Aspose.PDF एक शक्तिशाली व्यावसायिक लाइब्रेरी है, लेकिन यह परीक्षण और मूल्यांकन के लिए एक निःशुल्क परीक्षण संस्करण प्रदान करता है। अपने प्रोजेक्ट की आवश्यकताओं के आधार पर, आप एक उपयुक्त लाइसेंसिंग विकल्प चुन सकते हैं।

### 4. क्या मैं लंबवत टेक्स्ट बनाने के लिए टेक्स्ट को 90 डिग्री तक घुमा सकता हूँ?
   हाँ, आप लंबवत टेक्स्ट बनाने के लिए टेक्स्ट को 90 डिग्री तक घुमा सकते हैं। बस रोटेशन कोण को 90 डिग्री पर सेट करें, और टेक्स्ट पृष्ठ पर लंबवत दिखाई देगा।

### 5. क्या जावा में पीडीएफ के साथ काम करने के लिए अन्य लाइब्रेरी हैं?
   हां, जावा में पीडीएफ हेरफेर के लिए iText और PDFBox जैसी कई लाइब्रेरी उपलब्ध हैं। प्रत्येक लाइब्रेरी की अपनी अनूठी विशेषताएं और क्षमताएं होती हैं, इसलिए वह चुनें जो आपके प्रोजेक्ट की आवश्यकताओं के लिए सबसे उपयुक्त हो।