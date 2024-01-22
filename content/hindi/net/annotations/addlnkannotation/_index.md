---
title: एलएनके एनोटेशन जोड़ें
linktitle: एलएनके एनोटेशन जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: चरण-दर-चरण मार्गदर्शिका और पूर्ण स्रोत कोड के साथ .NET के लिए Aspose.PDF का उपयोग करके C# में PDF दस्तावेज़ों में इंक एनोटेशन सुविधा जोड़ने का तरीका जानें।
type: docs
weight: 20
url: /hi/net/annotations/addlnkannotation/
---
.NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को विभिन्न PDF ऑपरेशन करने में सक्षम बनाती है। ऐसा ही एक ऑपरेशन पीडीएफ दस्तावेज़ों में इंक एनोटेशन जोड़ना है। इस लेख में, हम .NET के लिए Aspose.PDF का उपयोग करके इंक एनोटेशन जोड़ने के लिए C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे। आएँ शुरू करें!

## .NET के लिए Aspose.PDF के इंक एनोटेशन फ़ीचर को समझना

C# स्रोत कोड में गोता लगाने से पहले, आइए पहले समझें कि इंक एनोटेशन क्या है और इसके उपयोग क्या हैं।

इंक एनोटेशन पीडीएफ दस्तावेजों पर फ्रीफॉर्म स्याही एनोटेशन बनाने का एक तरीका है। यह आपको स्टाइलस या माउस से एनोटेशन बनाने की अनुमति देता है। यह सुविधा उन स्थितियों में उपयोगी है जहां आपको आरेख, रेखाचित्र या अन्य प्रकार के एनोटेशन बनाने की आवश्यकता होती है।

## चरण 1: एक नया दस्तावेज़ बनाना

पीडीएफ दस्तावेज़ में इंक एनोटेशन जोड़ने का पहला चरण दस्तावेज़ वर्ग का एक नया उदाहरण बनाना है। यह निम्नलिखित कोड स्निपेट का उपयोग करके प्राप्त किया गया है:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

यहां, हम दस्तावेज़ वर्ग का एक नया उदाहरण बनाते हैं और उसमें एक नया पृष्ठ जोड़ते हैं।

## चरण 2: इंक एनोटेशन बनाना

अगला कदम इंकएनोटेशन क्लास का एक उदाहरण बनाना है। यह निम्नलिखित कोड स्निपेट का उपयोग करके किया जाता है:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

यहां, हम पहले System.Drawing.Rectangel क्लास का उपयोग करके एक आयत बनाते हैं और इसे FromRect विधि का उपयोग करके Aspose.Pdf.Rectangle में परिवर्तित करते हैं। फिर हम आयत, बिंदुओं की एक सूची और उस पृष्ठ का उपयोग करके इंकएनोटेशन क्लास का एक उदाहरण बनाते हैं जहां एनोटेशन जोड़ा जाता है।

फिर हम इंकएनोटेशन के विभिन्न गुण सेट करते हैं, जैसे शीर्षक, रंग, कैप शैली, बॉर्डर और अस्पष्टता। अंत में, हम Annotations.Add पद्धति का उपयोग करके पृष्ठ पर एनोटेशन जोड़ते हैं।

## चरण 3: दस्तावेज़ सहेजना

अंतिम चरण पीडीएफ दस्तावेज़ को इंक एनोटेशन के साथ सहेजना है। यह निम्नलिखित कोड स्निपेट का उपयोग करके प्राप्त किया गया है:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

यहां, हम आउटपुट फ़ाइल नाम को डेटा निर्देशिका में जोड़ते हैं और सेव विधि का उपयोग करके दस्तावेज़ को सहेजते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके इंक एनोटेशन जोड़ने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// आउटपुट फ़ाइल सहेजें
doc.Save(dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में इंक एनोटेशन कैसे जोड़ा जाए। चरण-दर-चरण मार्गदर्शिका और दिए गए C# स्रोत कोड का पालन करके, डेवलपर्स अपने पीडीएफ प्रोसेसिंग अनुप्रयोगों में इंक एनोटेशन कार्यक्षमता को आसानी से लागू कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में इंक एनोटेशन क्या है?

उ: एक पीडीएफ दस्तावेज़ में एक इंक एनोटेशन उपयोगकर्ताओं को स्टाइलस या माउस का उपयोग करके फ्रीफॉर्म स्याही एनोटेशन बनाने की अनुमति देता है। इसका उपयोग आमतौर पर पीडीएफ में हाथ से बनाए गए रेखाचित्र, आरेख या अन्य फ्रीहैंड एनोटेशन जोड़ने के लिए किया जाता है।

#### प्रश्न: क्या मैं इंक एनोटेशन के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हाँ, .NET के लिए Aspose.PDF इंक एनोटेशन की उपस्थिति को अनुकूलित करने के लिए विभिन्न गुण प्रदान करता है, जैसे कि रंग, अस्पष्टता, कैप शैली, बॉर्डर चौड़ाई, और बहुत कुछ। डेवलपर्स अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए इन संपत्तियों को समायोजित कर सकते हैं।

#### प्रश्न: क्या एक ही पीडीएफ पेज पर एकाधिक इंक एनोटेशन जोड़ना संभव है?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके एक ही पीडीएफ पेज पर एकाधिक इंक एनोटेशन जोड़ सकते हैं। प्रत्येक इंक एनोटेशन में बिंदुओं का अपना सेट और अनुकूलित स्वरूप हो सकता है।

#### प्रश्न: क्या मैं मौजूदा पीडीएफ दस्तावेज़ों में इंक एनोटेशन जोड़ सकता हूँ?

उत्तर: हाँ, .NET के लिए Aspose.PDF आपको नए बनाए गए PDF दस्तावेज़ों और मौजूदा PDF फ़ाइलों दोनों में इंक एनोटेशन जोड़ने की अनुमति देता है। आप मौजूदा पीडीएफ खोल सकते हैं, इंक एनोटेशन जोड़ सकते हैं और अपडेट किए गए दस्तावेज़ को सहेज सकते हैं।

#### प्रश्न: पीडीएफ दस्तावेजों में इंक एनोटेशन के लिए कुछ सामान्य उपयोग के मामले क्या हैं?

उत्तर: इंक एनोटेशन अनुप्रयोगों की एक विस्तृत श्रृंखला के लिए उपयोगी हैं, जिसमें पीडीएफ फॉर्म में हस्ताक्षर या हस्तलिखित नोट्स जोड़ना, वास्तुशिल्प ब्लूप्रिंट या इंजीनियरिंग चित्रों को एनोटेट करना और सहयोगात्मक समीक्षा के लिए दस्तावेजों को चिह्नित करना शामिल है।