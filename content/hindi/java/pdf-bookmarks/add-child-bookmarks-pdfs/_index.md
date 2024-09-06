---
title: पीडीएफ में चाइल्ड बुकमार्क जोड़ें
linktitle: पीडीएफ में चाइल्ड बुकमार्क जोड़ें
second_title: Aspose.PDF जावा पीडीएफ प्रसंस्करण एपीआई
description: जानें कि Java के लिए Aspose.PDF का उपयोग करके चाइल्ड बुकमार्क के साथ PDF दस्तावेज़ों को कैसे बेहतर बनाया जाए। बेहतर नेविगेशन और संगठन के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 11
url: /hi/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## पीडीएफ में चाइल्ड बुकमार्क जोड़ने का परिचय

इस लेख में, हम जावा के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ों में चाइल्ड बुकमार्क जोड़ने का तरीका जानेंगे। चाइल्ड बुकमार्क PDF दस्तावेज़ की सामग्री को व्यवस्थित करने और नेविगेट करने का एक सुविधाजनक तरीका है, जिससे उपयोगकर्ताओं के लिए दस्तावेज़ के भीतर विशिष्ट अनुभागों या विषयों को ढूंढना आसान हो जाता है।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा विकास वातावरण स्थापित है।
-  Aspose.PDF for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/java/).

## वातावरण की स्थापना

1. दिए गए लिंक से Java लाइब्रेरी के लिए Aspose.PDF डाउनलोड करें।
2. अपने जावा प्रोजेक्ट में लाइब्रेरी जोड़ें.

अब, आइए एक नया पीडीएफ दस्तावेज़ बनाकर उसमें चरण दर चरण चाइल्ड बुकमार्क जोड़ना शुरू करें।

## नया PDF दस्तावेज़ बनाना

आरंभ करने के लिए, हमें एक PDF दस्तावेज़ आरंभ करना होगा और उसमें पृष्ठ जोड़ने होंगे। आरंभ करने के लिए कोड स्निपेट यहां दिया गया है:

```java
// PDF दस्तावेज़ आरंभ करें
Document pdfDocument = new Document();

// पीडीएफ में पृष्ठ जोड़ें
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

इस उदाहरण में, हमने एक नया PDF दस्तावेज़ बनाया है और उसमें दो पृष्ठ जोड़े हैं।

## मूल बुकमार्क जोड़ना

पैरेंट बुकमार्क आपके PDF दस्तावेज़ में मुख्य अनुभाग या श्रेणियों के रूप में काम करते हैं। आइए कुछ पैरेंट बुकमार्क बनाएँ:

```java
// मूल बुकमार्क बनाएं
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

हमने दो मूल बुकमार्क जोड़े हैं, "मूल बुकमार्क 1" और "मूल बुकमार्क 2."

## चाइल्ड बुकमार्क जोड़ना

अब, हमारे द्वारा पहले बनाए गए पैरेंट बुकमार्क में चाइल्ड बुकमार्क जोड़ने का समय आ गया है। चाइल्ड बुकमार्क प्रत्येक पैरेंट बुकमार्क के भीतर विशिष्ट विषयों या उप-अनुभागों का प्रतिनिधित्व करते हैं। यहाँ बताया गया है कि आप इसे कैसे कर सकते हैं:

```java
// चाइल्ड बुकमार्क को पैरेंट बुकमार्क 1 में जोड़ें
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//चाइल्ड बुकमार्क को पैरेंट बुकमार्क 2 में जोड़ें
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

हमने "पैरेंट बुकमार्क 1" और "पैरेंट बुकमार्क 2" दोनों में चाइल्ड बुकमार्क जोड़ दिए हैं।

## बुकमार्क का स्वरूप अनुकूलित करना

आप बुकमार्क के टेक्स्ट और स्टाइल को बदलकर उनके स्वरूप को कस्टमाइज़ कर सकते हैं। इसके अतिरिक्त, आप बेहतर विज़ुअल प्रतिनिधित्व के लिए बुकमार्क में आइकन जोड़ सकते हैं। इसे कैसे करें, इसका एक उदाहरण यहां दिया गया है:

```java
// बुकमार्क का स्वरूप अनुकूलित करें
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

इस उदाहरण में, हमने पैरेंट बुकमार्क को इटैलिक बनाया है, चाइल्ड बुकमार्क के टेक्स्ट का रंग बदलकर हरा कर दिया है, तथा चाइल्ड बुकमार्क में इटैलिक आइकन जोड़ दिया है।

## घटनाओं को संभालना

बुकमार्क के साथ क्रियाएँ भी जुड़ी हो सकती हैं। उदाहरण के लिए, आप ऐसी क्रियाएँ जोड़ सकते हैं जो तब ट्रिगर होती हैं जब कोई उपयोगकर्ता बुकमार्क पर क्लिक करता है। यहाँ बताया गया है कि आप बुकमार्क क्लिक ईवेंट को कैसे संभाल सकते हैं:

```java
// बुकमार्क में कोई क्रिया जोड़ें
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

इस कोड में, हमने चाइल्ड बुकमार्क में "GoTo" क्रिया जोड़ी है जो क्लिक करने पर उपयोगकर्ता को पीडीएफ के दूसरे पृष्ठ पर ले जाएगी।

## पीडीएफ को सहेजना

एक बार जब आप सभी आवश्यक बुकमार्क जोड़ लेते हैं और उनके स्वरूप और क्रियाओं को अनुकूलित कर लेते हैं, तो आप संशोधित पीडीएफ दस्तावेज़ को सहेज सकते हैं:

```java
// पीडीएफ दस्तावेज़ सहेजें
pdfDocument.save("output.pdf");
```

अब आपका चाइल्ड बुकमार्क्स वाला पीडीएफ दस्तावेज़ तैयार है।

## संपूर्ण स्रोत कोड

जावा के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में चाइल्ड बुकमार्क जोड़ने के लिए पूरा स्रोत कोड यहां दिया गया है:

```java
// PDF दस्तावेज़ आरंभ करें
Document pdfDocument = new Document();

// पीडीएफ में पृष्ठ जोड़ें
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// मूल बुकमार्क बनाएं
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// चाइल्ड बुकमार्क को पैरेंट बुकमार्क 1 में जोड़ें
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//चाइल्ड बुकमार्क को पैरेंट बुकमार्क 2 में जोड़ें
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// बुकमार्क का स्वरूप अनुकूलित करें
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// बुकमार्क में कोई क्रिया जोड़ें
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// पीडीएफ दस्तावेज़ सहेजें
pdfDocument.save("output.pdf");
```

## निष्कर्ष

Aspose.PDF for Java का उपयोग करके PDF में चाइल्ड बुकमार्क जोड़ना एक शक्तिशाली सुविधा है जो आपके दस्तावेज़ों के नेविगेशन और संगठन को बेहतर बनाती है। इस लेख में बताए गए चरणों का पालन करके, आप पैरेंट और चाइल्ड बुकमार्क के साथ अच्छी तरह से संरचित PDF बना सकते हैं, उनकी उपस्थिति को अनुकूलित कर सकते हैं, और यहां तक कि उपयोगकर्ता अनुभव को बेहतर बनाने के लिए क्रियाएँ भी जोड़ सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.PDF कैसे डाउनलोड कर सकता हूँ?

 आप वेबसाइट से Java के लिए Aspose.PDF डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/java/).

### क्या सभी PDF व्यूअर्स में चाइल्ड बुकमार्क समर्थित हैं?

हां, अधिकांश आधुनिक पीडीएफ व्यूअर्स में चाइल्ड बुकमार्क समर्थित हैं और पीडीएफ दस्तावेजों में नेविगेट करने के लिए बेहतर उपयोगकर्ता अनुभव प्रदान करते हैं।

### क्या मैं बुकमार्क्स के स्वरूप को और अधिक अनुकूलित कर सकता हूँ?

हां, आप अपने दस्तावेज़ के डिज़ाइन के अनुरूप पाठ शैलियों, रंगों और आइकन को समायोजित करके बुकमार्क्स के स्वरूप को अनुकूलित कर सकते हैं।

### मैं बुकमार्क में अन्य कौन सी क्रियाएं जोड़ सकता हूं?

"GoTo" क्रियाओं के अतिरिक्त, आप वेब लिंक खोलने के लिए "URI" क्रियाएं या बुकमार्क पर क्लिक करने पर कस्टम स्क्रिप्ट निष्पादित करने के लिए "JavaScript" क्रियाएं जोड़ सकते हैं।

### क्या Aspose.PDF for Java व्यावसायिक परियोजनाओं के लिए उपयुक्त है?

हां, Java के लिए Aspose.PDF व्यक्तिगत और व्यावसायिक दोनों परियोजनाओं के लिए उपयुक्त है, और यह PDF हेरफेर और निर्माण के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।