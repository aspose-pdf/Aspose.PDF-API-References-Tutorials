---
title: पीडीएफ फाइल में बुकमार्क जोड़ें
linktitle: पीडीएफ फाइल में बुकमार्क जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ बेहतर नेविगेशन के लिए पीडीएफ फाइल में आसानी से बुकमार्क जोड़ें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/add-bookmark/
---
पीडीएफ फाइल में बुकमार्क जोड़ने से आसान और त्वरित नेविगेशन संभव हो जाता है। .NET के लिए Aspose.PDF के साथ, आप निम्नलिखित स्रोत कोड का पालन करके आसानी से PDF फ़ाइल में एक बुकमार्क जोड़ सकते हैं:

## चरण 1: आवश्यक पुस्तकालय आयात करें

शुरू करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करनी होगी। यहाँ आवश्यक आयात निर्देश है:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## चरण 2: दस्तावेज़ फ़ोल्डर में पथ सेट करें

 इस चरण में, आपको उस पीडीएफ फ़ाइल वाले फ़ोल्डर का पथ निर्दिष्ट करना होगा जिसमें आप बुकमार्क जोड़ना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"`आपके दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 3: पीडीएफ दस्तावेज़ खोलें

अब हम पीडीएफ दस्तावेज़ खोलेंगे जिसमें हम निम्नलिखित कोड का उपयोग करके एक बुकमार्क जोड़ना चाहते हैं:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## चरण 4: बुकमार्क ऑब्जेक्ट बनाएं

 इस चरण में, हम इसका उपयोग करके एक बुकमार्क ऑब्जेक्ट बनाएंगे`OutlineItemCollection` क्लास बनाएं और क्लिक करने पर उसके गुण जैसे शीर्षक, इटैलिक विशेषता, बोल्ड विशेषता और कार्रवाई सेट करें। यहाँ संबंधित कोड है:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## चरण 5: दस्तावेज़ में बुकमार्क जोड़ें

 अंत में, हम बनाए गए बुकमार्क को दस्तावेज़ के बुकमार्क संग्रह में जोड़ते हैं`Add` की विधि`Outlines` संपत्ति। यहाँ संबंधित कोड है:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### .NET के लिए Aspose.PDF का उपयोग करके बुकमार्क जोड़ें के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// एक बुकमार्क ऑब्जेक्ट बनाएं
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// गंतव्य पृष्ठ संख्या निर्धारित करें
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// दस्तावेज़ की रूपरेखा संग्रह में बुकमार्क जोड़ें।
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// आउटपुट सहेजें
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF का उपयोग करके बुकमार्क जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका है। आप कस्टम बुकमार्क जोड़कर अपने पीडीएफ दस्तावेजों में नेविगेशन को बेहतर बनाने के लिए इस कोड का उपयोग कर सकते हैं।

उन्नत बुकमार्क हेरफेर सुविधाओं पर अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ को अवश्य देखें।


### पीडीएफ फ़ाइल में बुकमार्क जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ फाइल में बुकमार्क क्या हैं?

उ: बुकमार्क, जिन्हें रूपरेखा के रूप में भी जाना जाता है, इंटरैक्टिव तत्व हैं जो पीडीएफ दस्तावेज़ के भीतर नेविगेशन और संरचना प्रदान करते हैं। वे उपयोगकर्ताओं को तुरंत विशिष्ट अनुभागों या पृष्ठों पर जाने की अनुमति देते हैं।

#### प्रश्न: मुझे पीडीएफ फाइल में बुकमार्क जोड़ने की आवश्यकता क्यों होगी?

उ: पीडीएफ फ़ाइल में बुकमार्क जोड़ने से उपयोगकर्ता अनुभव में सुधार होता है और पाठकों के लिए दस्तावेज़ की सामग्री के माध्यम से नेविगेट करना आसान हो जाता है। बुकमार्क सामग्री तालिका के रूप में काम कर सकते हैं या महत्वपूर्ण अनुभागों तक त्वरित पहुंच प्रदान कर सकते हैं।

#### प्रश्न: मैं अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी कैसे आयात करूं?

उ: अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करने के लिए, निम्नलिखित आयात निर्देश शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

ये निर्देश आपको पीडीएफ दस्तावेज़ों और बुकमार्क के साथ काम करने के लिए आवश्यक कक्षाओं और विधियों तक पहुंचने में सक्षम बनाते हैं।

#### प्रश्न: मैं दस्तावेज़ फ़ोल्डर का पथ कैसे निर्दिष्ट करूं?

 ए: बदलें`"YOUR DOCUMENT DIRECTORY"` दिए गए स्रोत कोड में उस पीडीएफ फ़ाइल वाले फ़ोल्डर के वास्तविक पथ के साथ जिसमें आप बुकमार्क जोड़ना चाहते हैं।

#### प्रश्न: मैं बुकमार्क जोड़ने के लिए पीडीएफ दस्तावेज़ कैसे खोलूं?

उ: बुकमार्क जोड़ने के लिए पीडीएफ दस्तावेज़ खोलने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 प्रतिस्थापित करें`"AddBookmark.pdf"` वास्तविक फ़ाइल नाम के साथ.

#### प्रश्न: मैं बुकमार्क ऑब्जेक्ट कैसे बनाऊं?

 उ: बुकमार्क ऑब्जेक्ट बनाने के लिए, का उपयोग करें`OutlineItemCollection` कक्षा। क्लिक करने पर इसके गुणों जैसे शीर्षक, इटैलिक शैली, बोल्ड शैली और क्रिया को अनुकूलित करें।

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  प्रश्न: इसका उद्देश्य क्या है?`Action` property in a bookmark?

 ए: द`Action` प्रॉपर्टी बुकमार्क पर क्लिक करने पर की जाने वाली क्रिया को निर्दिष्ट करती है। इस उदाहरण में, हम इसका उपयोग करते हैं`GoToAction`किसी विशिष्ट पृष्ठ पर नेविगेट करने के लिए कक्षा (इस मामले में पृष्ठ 2)।

#### प्रश्न: मैं दस्तावेज़ में बुकमार्क कैसे जोड़ूँ?

 ए: का प्रयोग करें`Add` की विधि`Outlines` दस्तावेज़ के बुकमार्क संग्रह में बनाए गए बुकमार्क को जोड़ने के लिए संपत्ति।

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### प्रश्न: क्या मैं इस पद्धति का उपयोग करके एकाधिक बुकमार्क जोड़ सकता हूँ?

उ: हाँ, आप दस्तावेज़ में एकाधिक बुकमार्क जोड़ने के लिए चरण 4 से 8 दोहरा सकते हैं। प्रत्येक बुकमार्क के गुणों और क्रियाओं को आवश्यकतानुसार अनुकूलित करें।

#### प्रश्न: मैं अद्यतन पीडीएफ फाइल को कैसे सहेजूं?

 उ: का उपयोग करके अद्यतन पीडीएफ फ़ाइल को सहेजें`Save` की विधि`pdfDocument` वस्तु:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### प्रश्न: मैं कैसे पुष्टि कर सकता हूं कि बुकमार्क जोड़ दिए गए हैं?

उ: यह सत्यापित करने के लिए कि दस्तावेज़ में निर्दिष्ट बुकमार्क जोड़े गए हैं, जेनरेट की गई पीडीएफ फ़ाइल खोलें।

#### प्रश्न: क्या मेरे द्वारा जोड़े जाने वाले बुकमार्क की संख्या की कोई सीमा है?

उ: आम तौर पर आपके द्वारा जोड़े जा सकने वाले बुकमार्क की संख्या की कोई सख्त सीमा नहीं है, लेकिन इष्टतम प्रदर्शन के लिए दस्तावेज़ के आकार और जटिलता पर विचार करें।

#### प्रश्न: क्या मैं बुकमार्क का स्वरूप अनुकूलित कर सकता हूँ?

उ: हां, आप Aspose.PDF सुविधाओं का उपयोग करके बुकमार्क उपस्थिति, रंग, शैली और अन्य विशेषताओं को और अधिक अनुकूलित कर सकते हैं।