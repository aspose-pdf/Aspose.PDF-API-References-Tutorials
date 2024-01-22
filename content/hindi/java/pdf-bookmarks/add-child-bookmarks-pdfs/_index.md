---
title: पीडीएफ़ में चाइल्ड बुकमार्क जोड़ें
linktitle: पीडीएफ़ में चाइल्ड बुकमार्क जोड़ें
second_title: Aspose.PDF जावा पीडीएफ प्रोसेसिंग एपीआई
description: जानें कि जावा के लिए Aspose.PDF का उपयोग करके चाइल्ड बुकमार्क के साथ पीडीएफ दस्तावेज़ों को कैसे बढ़ाया जाए। बेहतर नेविगेशन और संगठन के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 11
url: /hi/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## पीडीएफ़ में चाइल्ड बुकमार्क जोड़ने का परिचय

इस लेख में, हम यह पता लगाएंगे कि जावा के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ों में चाइल्ड बुकमार्क कैसे जोड़ें। चाइल्ड बुकमार्क पीडीएफ दस्तावेज़ की सामग्री को व्यवस्थित करने और नेविगेट करने का एक सुविधाजनक तरीका है, जिससे उपयोगकर्ताओं के लिए दस्तावेज़ के भीतर विशिष्ट अनुभाग या विषय ढूंढना आसान हो जाता है।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा विकास वातावरण स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.PDF। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/java/).

## पर्यावरण की स्थापना

1. दिए गए लिंक से जावा लाइब्रेरी के लिए Aspose.PDF डाउनलोड करें।
2. अपने जावा प्रोजेक्ट में लाइब्रेरी जोड़ें।

अब, आइए एक नया पीडीएफ दस्तावेज़ बनाकर और उसमें चरण दर चरण चाइल्ड बुकमार्क जोड़कर शुरुआत करें।

## एक नया पीडीएफ दस्तावेज़ बनाना

आरंभ करने के लिए, हमें एक पीडीएफ दस्तावेज़ आरंभ करना होगा और उसमें पेज जोड़ना होगा। आरंभ करने के लिए यहां कोड स्निपेट दिया गया है:

```java
// एक पीडीएफ दस्तावेज़ प्रारंभ करें
Document pdfDocument = new Document();

// पीडीएफ में पेज जोड़ें
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

इस उदाहरण में, हमने एक नया पीडीएफ दस्तावेज़ बनाया है और इसमें दो पेज जोड़े हैं।

## पेरेंट बुकमार्क जोड़ना

पेरेंट बुकमार्क आपके पीडीएफ दस्तावेज़ में मुख्य अनुभाग या श्रेणियों के रूप में कार्य करते हैं। आइए कुछ पेरेंट बुकमार्क बनाएं:

```java
// मूल बुकमार्क बनाएँ
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

हमने दो मूल बुकमार्क, "पैरेंट बुकमार्क 1" और "पैरेंट बुकमार्क 2" जोड़े हैं।

## चाइल्ड बुकमार्क जोड़ना

अब, हमारे द्वारा पहले बनाए गए मूल बुकमार्क में चाइल्ड बुकमार्क जोड़ने का समय आ गया है। चाइल्ड बुकमार्क प्रत्येक मूल बुकमार्क के भीतर विशिष्ट विषयों या उप-अनुभागों का प्रतिनिधित्व करते हैं। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
// पेरेंट बुकमार्क 1 में चाइल्ड बुकमार्क जोड़ें
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//पेरेंट बुकमार्क 2 में चाइल्ड बुकमार्क जोड़ें
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

हमने "पैरेंट बुकमार्क 1" और "पैरेंट बुकमार्क 2" दोनों में चाइल्ड बुकमार्क जोड़ दिए हैं।

## बुकमार्क उपस्थिति को अनुकूलित करना

आप बुकमार्क के टेक्स्ट और शैली को बदलकर उनके स्वरूप को अनुकूलित कर सकते हैं। इसके अतिरिक्त, आप बेहतर दृश्य प्रतिनिधित्व के लिए बुकमार्क में आइकन जोड़ सकते हैं। इसे कैसे करें इसका एक उदाहरण यहां दिया गया है:

```java
// बुकमार्क उपस्थिति को अनुकूलित करें
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

इस उदाहरण में, हमने पैरेंट बुकमार्क को इटैलिक बना दिया है, चाइल्ड बुकमार्क के टेक्स्ट का रंग बदलकर हरा कर दिया है, और चाइल्ड बुकमार्क में एक इटैलिक आइकन जोड़ दिया है।

## घटनाओं को संभालना

बुकमार्क के साथ क्रियाएँ भी जुड़ी हो सकती हैं। उदाहरण के लिए, आप ऐसी कार्रवाइयां जोड़ सकते हैं जो उपयोगकर्ता द्वारा किसी बुकमार्क पर क्लिक करने पर ट्रिगर हो जाती हैं। यहां बताया गया है कि आप बुकमार्क क्लिक ईवेंट को कैसे प्रबंधित कर सकते हैं:

```java
// बुकमार्क में कोई क्रिया जोड़ें
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

इस कोड में, हमने चाइल्ड बुकमार्क में एक "GoTo" क्रिया जोड़ी है जो क्लिक करने पर उपयोगकर्ता को पीडीएफ के दूसरे पृष्ठ पर ले जाएगी।

## पीडीएफ सहेजा जा रहा है

एक बार जब आप सभी आवश्यक बुकमार्क जोड़ लेते हैं और उनकी उपस्थिति और क्रियाओं को अनुकूलित कर लेते हैं, तो आप संशोधित पीडीएफ दस्तावेज़ को सहेज सकते हैं:

```java
// पीडीएफ दस्तावेज़ सहेजें
pdfDocument.save("output.pdf");
```

चाइल्ड बुकमार्क के साथ आपका पीडीएफ दस्तावेज़ अब तैयार है।

## संपूर्ण स्रोत कोड

जावा के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में चाइल्ड बुकमार्क जोड़ने का संपूर्ण स्रोत कोड यहां दिया गया है:

```java
// एक पीडीएफ दस्तावेज़ प्रारंभ करें
Document pdfDocument = new Document();

// पीडीएफ में पेज जोड़ें
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// मूल बुकमार्क बनाएँ
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// पेरेंट बुकमार्क 1 में चाइल्ड बुकमार्क जोड़ें
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//पेरेंट बुकमार्क 2 में चाइल्ड बुकमार्क जोड़ें
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// बुकमार्क उपस्थिति को अनुकूलित करें
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

जावा के लिए Aspose.PDF का उपयोग करके PDF में चाइल्ड बुकमार्क जोड़ना एक शक्तिशाली सुविधा है जो आपके दस्तावेज़ों के नेविगेशन और संगठन को बढ़ाती है। इस आलेख में उल्लिखित चरणों का पालन करके, आप माता-पिता और बच्चे के बुकमार्क के साथ अच्छी तरह से संरचित पीडीएफ बना सकते हैं, उनकी उपस्थिति को अनुकूलित कर सकते हैं, और यहां तक कि उपयोगकर्ता अनुभव को बढ़ाने के लिए क्रियाएं भी जोड़ सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.PDF कैसे डाउनलोड कर सकता हूँ?

 आप वेबसाइट से जावा के लिए Aspose.PDF डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/java/).

### क्या चाइल्ड बुकमार्क सभी पीडीएफ व्यूअर्स में समर्थित हैं?

हां, अधिकांश आधुनिक पीडीएफ व्यूअर्स में चाइल्ड बुकमार्क समर्थित हैं और पीडीएफ दस्तावेजों के माध्यम से नेविगेट करने के लिए एक बेहतर उपयोगकर्ता अनुभव प्रदान करते हैं।

### क्या मैं बुकमार्क के स्वरूप को और अधिक अनुकूलित कर सकता हूँ?

हां, आप अपने दस्तावेज़ के डिज़ाइन के अनुरूप टेक्स्ट शैलियों, रंगों और आइकन को समायोजित करके बुकमार्क की उपस्थिति को अनुकूलित कर सकते हैं।

### मैं बुकमार्क में और कौन सी क्रियाएँ जोड़ सकता हूँ?

"GoTo" क्रियाओं के अलावा, आप वेब लिंक खोलने के लिए "URI" क्रियाएं या किसी बुकमार्क पर क्लिक करने पर कस्टम स्क्रिप्ट निष्पादित करने के लिए "जावास्क्रिप्ट" क्रियाएं जोड़ सकते हैं।

### क्या जावा के लिए Aspose.PDF व्यावसायिक परियोजनाओं के लिए उपयुक्त है?

हां, जावा के लिए Aspose.PDF व्यक्तिगत और व्यावसायिक दोनों परियोजनाओं के लिए उपयुक्त है, और यह पीडीएफ हेरफेर और पीढ़ी के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।