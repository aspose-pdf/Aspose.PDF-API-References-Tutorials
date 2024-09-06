---
title: जावा का उपयोग करके पीडीएफ में टेक्स्ट संरचना को स्टाइल करें
linktitle: जावा का उपयोग करके पीडीएफ में टेक्स्ट संरचना को स्टाइल करें
second_title: Aspose.PDF जावा पीडीएफ प्रसंस्करण एपीआई
description: हमारे चरण-दर-चरण गाइड के साथ जावा का उपयोग करके PDF में टेक्स्ट संरचनाओं को स्टाइल करना सीखें। पेशेवर दिखने वाले दस्तावेज़ों के लिए फ़ॉन्ट, रंग, हाइपरलिंक और बहुत कुछ कस्टमाइज़ करें।
type: docs
weight: 11
url: /hi/java/pdf-styles-and-formatting/style-text-structure-in-pdf-using-java/
---

## परिचय

पीडीएफ दस्तावेज़, रिपोर्ट और विभिन्न प्रकार की सामग्री साझा करने के लिए एक मानक प्रारूप बन गया है। जावा में पीडीएफ के साथ काम करते समय, न केवल उन्हें डेटा से भरना आवश्यक है, बल्कि एक पॉलिश उपस्थिति के लिए पाठ को स्टाइल करना भी आवश्यक है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा डेवलपमेंट किट (JDK) स्थापित.
- Aspose.PDF for Java लाइब्रेरी डाउनलोड और सेट अप की गई।

## वातावरण की स्थापना

जावा का उपयोग करके पीडीएफ में टेक्स्ट को स्टाइल करना शुरू करने के लिए, आपको अपना डेवलपमेंट एनवायरनमेंट सेट अप करना होगा। इन चरणों का पालन करें:

1.  Aspose.PDF for Java लाइब्रेरी को यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/pdf/java/).

2. अपने जावा प्रोजेक्ट में लाइब्रेरी को शामिल करें।

3. अपने कोड में Aspose.PDF से आवश्यक क्लासेस आयात करें।

## पीडीएफ में पाठ जोड़ना

अब, आइए PDF दस्तावेज़ में टेक्स्ट जोड़ना शुरू करें। यहाँ एक सरल उदाहरण दिया गया है:

```java
// एक नया PDF दस्तावेज़ बनाएँ
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();

// दस्तावेज़ में एक पृष्ठ जोड़ें
pdfDocument.getPages().add();

// एक TextFragment ऑब्जेक्ट बनाएँ
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment("Hello, PDF!");

// पृष्ठ पर TextFragment जोड़ें
pdfDocument.getPages().get_Item(1).getParagraphs().add(textFragment);

// दस्तावेज़ सहेजें
pdfDocument.save("output.pdf");
```

यह कोड एक पीडीएफ दस्तावेज़ बनाता है, एक पृष्ठ जोड़ता है, तथा पृष्ठ पर "हैलो, पीडीएफ!" पाठ सम्मिलित करता है।

## फ़ॉन्ट स्टाइलिंग

आप अपने टेक्स्ट का फ़ॉन्ट कस्टमाइज़ कर सकते हैं। फ़ॉन्ट फ़ैमिली और आकार बदलने का तरीका यहां बताया गया है:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
textFragment.getTextState().setFontSize(12);
```

## पाठ का आकार और रंग

पाठ का आकार और रंग समायोजित करना सरल है:

```java
textFragment.getTextState().setFontSize(16);
textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getBlue());
```

## पाठ संरेखण

अपने PDF में पाठ संरेखण नियंत्रित करें:

```java
textFragment.getTextState().setHorizontalAlignment(HorizontalAlignment.Center);
```

## शीर्षलेख और पादलेख जोड़ना

शीर्षलेख और पादलेख के साथ दस्तावेज़ संरचना को बेहतर बनाएँ:

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

अपने PDF में व्यवस्थित सूचियाँ बनाएँ:

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
link.setAction(new GoToURIAction("https://www.example.com"));

page.getParagraphs().add(link);
```

## पाठ रूपांतरण

आवश्यकतानुसार पाठ को रूपांतरित करें:

```java
textFragment.getTextState().setTextRise(5); // पाठ को ऊपर उठाता है
textFragment.getTextState().setTextScaling(200); // पाठ को मापता है
textFragment.getTextState().setUnderline(true);
```

## पेज लेआउट और मार्जिन

अपने PDF पृष्ठों के लेआउट को नियंत्रित करें:

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

इस गाइड में, हमने Aspose.PDF की मदद से जावा का उपयोग करके PDF में टेक्स्ट संरचनाओं को स्टाइल करने का तरीका खोजा है। अब आप अपनी विशिष्ट आवश्यकताओं को पूरा करने वाले दिखने में आकर्षक और अच्छी तरह से संरचित PDF दस्तावेज़ बना सकते हैं। प्रदान की गई तकनीकों के साथ प्रयोग करें और अपने PDF निर्माण कौशल को बढ़ाएँ।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पीडीएफ में टेक्स्ट का फ़ॉन्ट कैसे बदलूं?

 पीडीएफ में टेक्स्ट का फ़ॉन्ट बदलने के लिए, का उपयोग करें`setTextState()` विधि का उपयोग करके वांछित फ़ॉन्ट निर्दिष्ट करें`setFont()`। उदाहरण के लिए:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
```

### क्या मैं Java के लिए Aspose.PDF का उपयोग करके अपने PDF में हाइपरलिंक जोड़ सकता हूँ?

 हां, आप जावा के लिए Aspose.PDF का उपयोग करके अपने पीडीएफ में हाइपरलिंक जोड़ सकते हैं।`Hyperlink` लिंक बनाने और क्रियाएँ निर्दिष्ट करने के लिए क्लास, जैसे URL खोलना।

### पीडीएफ में पृष्ठ विराम को संभालने का अनुशंसित तरीका क्या है?

 PDF में पृष्ठ विराम को संभालने के लिए, सेट करें`IsAutoTruncated` और`IsWordWrapped` गुण`true` में`TextState`यह सुनिश्चित करता है कि पाठ को पृष्ठ की सीमाओं के भीतर फिट करने के लिए ठीक से काटा और लपेटा गया है।

### मैं अपने पीडीएफ दस्तावेज़ों को वॉटरमार्क से कैसे सुरक्षित रख सकता हूँ?

आप PDF में वॉटरमार्क टेक्स्ट फ़्रैगमेंट जोड़कर अपने PDF दस्तावेज़ों को वॉटरमार्क से सुरक्षित कर सकते हैं। वांछित प्रभाव प्राप्त करने के लिए वॉटरमार्क की उपस्थिति, जैसे फ़ॉन्ट आकार और रंग को अनुकूलित करें।

### मैं Java के लिए Aspose.PDF के बारे में अधिक जानकारी और दस्तावेज़ कहां पा सकता हूं?

 आप Java के लिए Aspose.PDF का विस्तृत दस्तावेज़ीकरण यहां पा सकते हैं[यहाँ](https://reference.aspose.com/pdf/java/).