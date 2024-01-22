---
title: जावा का उपयोग करके पीडीएफ में स्टाइल टेक्स्ट संरचना
linktitle: जावा का उपयोग करके पीडीएफ में स्टाइल टेक्स्ट संरचना
second_title: Aspose.PDF जावा पीडीएफ प्रोसेसिंग एपीआई
description: हमारे चरण-दर-चरण मार्गदर्शिका से जानें कि जावा का उपयोग करके पीडीएफ में टेक्स्ट संरचनाओं को कैसे स्टाइल किया जाए। पेशेवर दिखने वाले दस्तावेज़ों के लिए फ़ॉन्ट, रंग, हाइपरलिंक और बहुत कुछ अनुकूलित करें।
type: docs
weight: 11
url: /hi/java/pdf-styles-and-formatting/style-text-structure-in-pdf-using-java/
---

## परिचय

पीडीएफ़ दस्तावेज़, रिपोर्ट और विभिन्न प्रकार की सामग्री साझा करने के लिए एक मानक प्रारूप बन गए हैं। जावा में पीडीएफ के साथ काम करते समय, न केवल उनमें डेटा भरना आवश्यक है, बल्कि एक बेहतर स्वरूप के लिए टेक्स्ट को स्टाइल करना भी आवश्यक है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया।
- जावा लाइब्रेरी के लिए Aspose.PDF डाउनलोड और सेट अप करें।

## पर्यावरण की स्थापना

जावा का उपयोग करके पीडीएफ में टेक्स्ट को स्टाइल करना शुरू करने के लिए, आपको अपना विकास वातावरण स्थापित करना होगा। इन चरणों का पालन करें:

1.  जावा लाइब्रेरी के लिए Aspose.PDF डाउनलोड करें[यहाँ](https://releases.aspose.com/pdf/java/).

2. अपने जावा प्रोजेक्ट में लाइब्रेरी शामिल करें।

3. अपने कोड में Aspose.PDF से आवश्यक कक्षाएं आयात करें।

## पीडीएफ में टेक्स्ट जोड़ना

अब, आइए एक पीडीएफ दस्तावेज़ में टेक्स्ट जोड़कर शुरुआत करें। यहाँ एक सरल उदाहरण है:

```java
// एक नया पीडीएफ दस्तावेज़ बनाएं
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();

// दस्तावेज़ में एक पृष्ठ जोड़ें
pdfDocument.getPages().add();

// एक टेक्स्टफ्रैगमेंट ऑब्जेक्ट बनाएं
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment("Hello, PDF!");

// पेज पर TextFragment जोड़ें
pdfDocument.getPages().get_Item(1).getParagraphs().add(textFragment);

// दस्तावेज़ सहेजें
pdfDocument.save("output.pdf");
```

यह कोड एक पीडीएफ दस्तावेज़ बनाता है, एक पेज जोड़ता है, और "हैलो, पीडीएफ!" टेक्स्ट सम्मिलित करता है। पेज पर.

## फ़ॉन्ट स्टाइलिंग

आप अपने टेक्स्ट का फ़ॉन्ट कस्टमाइज़ कर सकते हैं. यहां फ़ॉन्ट परिवार और आकार बदलने का तरीका बताया गया है:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
textFragment.getTextState().setFontSize(12);
```

## पाठ का आकार और रंग

टेक्स्ट का आकार और रंग समायोजित करना सरल है:

```java
textFragment.getTextState().setFontSize(16);
textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getBlue());
```

## पाठ्य संरेखण

अपने पीडीएफ में पाठ संरेखण को नियंत्रित करें:

```java
textFragment.getTextState().setHorizontalAlignment(HorizontalAlignment.Center);
```

## शीर्षलेख और पाद लेख जोड़ना

शीर्षलेख और पादलेख के साथ दस्तावेज़ संरचना बढ़ाएँ:

```java
Page page = pdfDocument.getPages().get_Item(1);
HeaderFooter header = new HeaderFooter();
page.setFooter(header);

TextFragment footerText = new TextFragment("Page Number: ");
header.getParagraphs().add(footerText);

footerText = new TextFragment("1");
footerText.getTextState().setFont(FontRepository.findFont("Arial"));
footerText.getTextState().setFontSize(12);
footerText.getTextState().setForegroundColor(com.aspose.pdf.Color.getBlack());

header.getParagraphs().add(footerText);
```

## बुलेटेड सूचियाँ जोड़ना

अपनी पीडीएफ में व्यवस्थित सूचियां बनाएं:

```java
ListSection listSection = new ListSection();
page.getParagraphs().add(listSection);

TextFragmentListItem listItem = new TextFragmentListItem("Item 1");
listItem.getSegments().get_Item(0).getTextState().setFont(FontRepository.findFont("Arial"));
listItem.getSegments().get_Item(0).getTextState().setFontSize(12);
listSection.getListItems().add(listItem);

listItem = new TextFragmentListItem("Item 2");
listItem.getSegments().get_Item(0).getTextState().setFont(FontRepository.findFont("Arial"));
listItem.getSegments().get_Item(0).getTextState().setFontSize(12);
listSection.getListItems().add(listItem);
```

## हाइपरलिंक बनाना

इंटरैक्टिव सामग्री के लिए अपने पीडीएफ में हाइपरलिंक जोड़ें:

```java
TextFragment linkText = new TextFragment("Visit our website");
linkText.getTextState().setFont(FontRepository.findFont("Arial"));
linkText.getTextState().setFontSize(12);

Hyperlink link = new Hyperlink(linkText);
link.setAction(new GoToURIAction("https://www.example.com");

page.getParagraphs().add(link);
```

## पाठ परिवर्तन

आवश्यकतानुसार टेक्स्ट को रूपांतरित करें:

```java
textFragment.getTextState().setTextRise(5); // पाठ को ऊपर उठाता है
textFragment.getTextState().setTextScaling(200); // पाठ को मापता है
textFragment.getTextState().setUnderline(true);
```

## पेज लेआउट और मार्जिन

अपने पीडीएफ पृष्ठों के लेआउट को नियंत्रित करें:

```java
page.setPageSize(PageSize.getA4());
page.getPageInfo().getMargin().setLeft(50);
page.getPageInfo().getMargin().setRight(50);
```

## पेज ब्रेक को संभालना

अपनी सामग्री के लिए उचित पृष्ठ विराम सुनिश्चित करें:

```java
textFragment.getTextState().setIsAutoTruncated(true);
textFragment.getTextState().setIsWordWrapped(true);
```

## वॉटरमार्क जोड़ना

अपनी सामग्री को वॉटरमार्क से सुरक्षित रखें:

```java
TextFragment watermark = new TextFragment("Confidential");
watermark.getTextState().setFont(FontRepository.findFont("Arial"));
watermark.getTextState().setFontSize(36);
watermark.getTextState().setForegroundColor(com.aspose.pdf.Color.getGray());

page.getParagraphs().add(watermark);
```

## निष्कर्ष

इस गाइड में, हमने Aspose.PDF की मदद से जावा का उपयोग करके पीडीएफ में टेक्स्ट संरचनाओं को कैसे स्टाइल किया जाए, इसका पता लगाया है। अब आप दिखने में आकर्षक और अच्छी तरह से संरचित पीडीएफ दस्तावेज़ बना सकते हैं जो आपकी विशिष्ट आवश्यकताओं को पूरा करते हैं। प्रदान की गई तकनीकों के साथ प्रयोग करें और अपने पीडीएफ निर्माण कौशल को बढ़ाएं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पीडीएफ में टेक्स्ट का फ़ॉन्ट कैसे बदलूं?

 पीडीएफ में टेक्स्ट का फ़ॉन्ट बदलने के लिए, इसका उपयोग करें`setTextState()` विधि और वांछित फ़ॉन्ट का उपयोग करके निर्दिष्ट करें`setFont()`. उदाहरण के लिए:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
```

### क्या मैं Java के लिए Aspose.PDF का उपयोग करके अपने PDF में हाइपरलिंक जोड़ सकता हूँ?

 हाँ, आप Java के लिए Aspose.PDF का उपयोग करके अपने PDF में हाइपरलिंक जोड़ सकते हैं। उपयोग`Hyperlink` लिंक बनाने और क्रियाएं निर्दिष्ट करने के लिए क्लास, जैसे यूआरएल खोलना।

### पीडीएफ में पेज ब्रेक को संभालने का अनुशंसित तरीका क्या है?

 पीडीएफ में पेज ब्रेक को संभालने के लिए, सेट करें`IsAutoTruncated` और`IsWordWrapped` गुण को`true` में`TextState`. यह सुनिश्चित करता है कि पाठ को पृष्ठ सीमाओं के भीतर फिट करने के लिए ठीक से काटा और लपेटा गया है।

### मैं अपने पीडीएफ दस्तावेज़ों को वॉटरमार्क से कैसे सुरक्षित रख सकता हूँ?

आप पीडीएफ में वॉटरमार्क टेक्स्ट टुकड़ा जोड़कर अपने पीडीएफ दस्तावेज़ों को वॉटरमार्क से सुरक्षित कर सकते हैं। वांछित प्रभाव प्राप्त करने के लिए वॉटरमार्क के स्वरूप, जैसे फ़ॉन्ट आकार और रंग, को अनुकूलित करें।

### जावा के लिए Aspose.PDF के लिए मुझे अधिक जानकारी और दस्तावेज़ कहां मिल सकते हैं?

 आप जावा के लिए Aspose.PDF के लिए व्यापक दस्तावेज़ यहां पा सकते हैं[यहाँ](https://reference.aspose.com/pdf/java/).