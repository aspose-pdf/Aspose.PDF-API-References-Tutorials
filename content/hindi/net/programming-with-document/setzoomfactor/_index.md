---
title: पीडीएफ फाइल में ज़ूम फैक्टर सेट करें
linktitle: पीडीएफ फाइल में ज़ूम फैक्टर सेट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: हमारे चरण-दर-चरण मार्गदर्शिका से जानें कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में ज़ूम फ़ैक्टर कैसे सेट करें।
type: docs
weight: 340
url: /hi/net/programming-with-document/setzoomfactor/
---
.NET के लिए Aspose.PDF एक शक्तिशाली API है जो डेवलपर्स को उनके .NET अनुप्रयोगों में PDF दस्तावेज़ों के साथ काम करने की अनुमति देता है। इसके द्वारा प्रदान की जाने वाली सुविधाओं में से एक पीडीएफ दस्तावेज़ के ज़ूम फैक्टर को सेट करने की क्षमता है। इस चरण-दर-चरण मार्गदर्शिका में, हम बताएंगे कि दिए गए C# स्रोत कोड का उपयोग करके PDF दस्तावेज़ के ज़ूम फ़ैक्टर को सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें।

## चरण 1: दस्तावेज़ निर्देशिका के लिए पथ सेट करें

 पहला कदम उस निर्देशिका के लिए पथ सेट करना है जहां पीडीएफ दस्तावेज़ स्थित है। इसे सेट करके किया जा सकता है`dataDir` निर्देशिका पथ के लिए परिवर्तनीय। 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"आपकी दस्तावेज़ निर्देशिका" को उस वास्तविक निर्देशिका पथ से बदलें जहां आपका पीडीएफ दस्तावेज़ स्थित है।

## चरण 2: एक नया दस्तावेज़ ऑब्जेक्ट इंस्टेंट करें

 .NET के लिए Aspose.PDF का उपयोग करके एक PDF दस्तावेज़ के साथ काम करने के लिए, हमें एक नया दस्तावेज़ बनाने की आवश्यकता है`Document` ऑब्जेक्ट करें और उसमें पीडीएफ फाइल लोड करें। 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 यह कोड एक नया बनाएगा`Document` ऑब्जेक्ट करें और "SetZoomFactor.pdf" नामक पीडीएफ फाइल को लोड करें`dataDir` इसमें निर्देशिका.

## चरण 3: ज़ूम फ़ैक्टर सेट करें

 एक बार`Document`ऑब्जेक्ट बन जाने पर, हम पीडीएफ दस्तावेज़ का ज़ूम फ़ैक्टर सेट कर सकते हैं। निम्नलिखित कोड में, हम ज़ूम फ़ैक्टर को 50% पर सेट करते हैं।

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 यह कोड एक नया बनाकर ज़ूम फ़ैक्टर को 50% पर सेट करता है`GoToAction` ऑब्जेक्ट और पासिंग ए`XYZExplicitDestination` 50% ज़ूम कारक वाली वस्तु।`OpenAction` की संपत्ति`Document` फिर ऑब्जेक्ट को इस पर सेट किया जाता है`GoToAction` वस्तु।

## चरण 4: पीडीएफ दस्तावेज़ सहेजें

 अंत में, हम संशोधित पीडीएफ दस्तावेज़ को एक नई फ़ाइल में सहेज सकते हैं। निम्नलिखित कोड में, हम पीडीएफ दस्तावेज़ को "Zoomed_pdf_out.pdf" नाम की एक नई फ़ाइल में सहेजते हैं`dataDir` निर्देशिका।

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके सेट ज़ूम फ़ैक्टर के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// नए दस्तावेज़ ऑब्जेक्ट को त्वरित करें
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// दस्तावेज़ सहेजें
doc.Save(dataDir);
```

## निष्कर्ष

.NET के लिए Aspose.PDF C# कोड का उपयोग करके PDF दस्तावेज़ के ज़ूम फ़ैक्टर को सेट करने का एक सरल और कुशल तरीका प्रदान करता है। उपरोक्त चरणों का पालन करके, आप अपने .NET एप्लिकेशन में किसी भी पीडीएफ दस्तावेज़ के ज़ूम फैक्टर को आसानी से संशोधित कर सकते हैं।

### पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में ज़ूम कारक क्या है, और यह देखने को कैसे प्रभावित करता है?

उ: पीडीएफ दस्तावेज़ में ज़ूम कारक दस्तावेज़ को देखे जाने पर आवर्धन का स्तर निर्धारित करता है। यह उस पैमाने को निर्दिष्ट करता है जिस पर दस्तावेज़ प्रदर्शित किया जाता है, जिससे यह प्रभावित होता है कि स्क्रीन पर सामग्री कितनी बड़ी या छोटी दिखाई देती है। 1.0 का ज़ूम कारक 100% ज़ूम (वास्तविक आकार) का प्रतिनिधित्व करता है, जबकि 1.0 से अधिक का कारक ज़ूम इन करता है, और 1.0 से कम का कारक ज़ूम आउट करता है।

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ के भीतर विभिन्न पृष्ठों के लिए एक विशिष्ट ज़ूम कारक सेट कर सकता हूँ?

 उ: हाँ, .NET के लिए Aspose.PDF के साथ, आप एक ही PDF दस्तावेज़ के भीतर विभिन्न पृष्ठों के लिए अलग-अलग ज़ूम कारक सेट कर सकते हैं। प्रदान किया गया उदाहरण स्रोत कोड दर्शाता है कि इसका उपयोग करके पहले पृष्ठ के लिए ज़ूम फ़ैक्टर कैसे सेट किया जाए`GoToAction` वस्तु। आप आवश्यकतानुसार अन्य पृष्ठों के लिए अलग-अलग ज़ूम कारक सेट करने के लिए कोड को संशोधित कर सकते हैं।

#### प्रश्न: ज़ूम फ़ैक्टर बदलने से पीडीएफ दस्तावेज़ की छपाई और बचत पर क्या प्रभाव पड़ता है?

उ: .NET के लिए Aspose.PDF का उपयोग करके ज़ूम फ़ैक्टर को बदलने से PDF दस्तावेज़ की वास्तविक सामग्री प्रभावित नहीं होती है। यह देखने के अनुभव को केवल तभी प्रभावित करता है जब दस्तावेज़ को पीडीएफ व्यूअर में खोला जाता है। प्रोग्रामेटिक रूप से सेट किया गया ज़ूम फ़ैक्टर मुद्रित आउटपुट या सहेजी गई पीडीएफ फ़ाइल को प्रभावित नहीं करेगा।