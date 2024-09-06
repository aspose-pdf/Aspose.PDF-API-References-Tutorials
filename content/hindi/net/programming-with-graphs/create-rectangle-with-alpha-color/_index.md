---
title: अल्फा रंग के साथ आयत बनाएँ
linktitle: अल्फा रंग के साथ आयत बनाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पारदर्शी रंग वाला आयत बनाना सीखें। पारदर्शिता को अनुकूलित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 60
url: /hi/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ एक आयत बनाने के लिए निम्नलिखित C# स्रोत कोड के माध्यम से चरण दर चरण मार्गदर्शन करेंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना डेवलपमेंट एनवायरनमेंट सेट कर लिया है। साथ ही C# प्रोग्रामिंग का बुनियादी ज्ञान भी रखें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए सोर्स कोड में, आपको वह डायरेक्टरी निर्दिष्ट करनी होगी जहाँ आप परिणामी PDF फ़ाइल को सहेजना चाहते हैं। "dataDir" वैरिएबल को वांछित डायरेक्टरी में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ ऑब्जेक्ट को इंस्टेंटिएट करना और पेज जोड़ना

हम डॉक्यूमेंट क्लास का एक उदाहरण बनाते हैं और इस डॉक्यूमेंट में एक पृष्ठ जोड़ते हैं।

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## चरण 3: एक ग्राफ ऑब्जेक्ट और एक आयत बनाना

हम निर्दिष्ट आयामों के साथ एक ग्राफ ऑब्जेक्ट और विशिष्ट आयामों के साथ एक आयत बनाते हैं।

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## चरण 4: आयत के लिए अल्फा रंग सेट करना

हम System.Drawing.Color वर्ग की FromArgb विधि का उपयोग करके आयत के लिए अल्फा रंग निर्दिष्ट कर सकते हैं।

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## चरण 5: ग्राफ़ ऑब्जेक्ट में आयत जोड़ना

हम आयत को ग्राफ ऑब्जेक्ट के आकार संग्रह में जोड़ते हैं।

```csharp
canvas.Shapes.Add(rect);
```

## चरण 6: एक अलग अल्फा रंग के साथ दूसरा आयत बनाना

हम विशिष्ट आयामों और एक अन्य अल्फा रंग के साथ एक दूसरा आयत बनाते हैं।

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## चरण 7: पृष्ठ पर ग्राफ़ ऑब्जेक्ट जोड़ना

हम ग्राफ ऑब्जेक्ट को पेज ऑब्जेक्ट के पैराग्राफ संग्रह में जोड़ते हैं।

```csharp
page.Paragraphs.Add(canvas);
```

## चरण 8: परिणामी पीडीएफ फाइल को सेव करना

अंत में, हम परिणामी PDF फ़ाइल को "CreateRectangleWithAlphaColor_out.pdf" नाम से निर्दिष्ट निर्देशिका में सहेजते हैं।

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ आयत बनाने के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ उदाहरण को तत्कालित करें
Document doc = new Document();
// पीडीएफ फाइल के पेज टू पेज संग्रह को जोड़ें
Aspose.Pdf.Page page = doc.Pages.Add();
// ग्राफ़ इंस्टेंस बनाएँ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// विशिष्ट आयामों के साथ आयताकार ऑब्जेक्ट बनाएँ
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// 32-बिट ARGB मान से System.Drawing.Color संरचना से ग्राफ भरण रंग सेट करें
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// ग्राफ़ इंस्टेंस के आकार संग्रह में आयत ऑब्जेक्ट जोड़ें
canvas.Shapes.Add(rect);
// दूसरा आयताकार ऑब्जेक्ट बनाएँ
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// पेज ऑब्जेक्ट के पैराग्राफ़ संग्रह में ग्राफ़ इंस्टेंस जोड़ें
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// पीडीएफ फाइल सहेजें
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने बताया कि .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ एक आयत कैसे बनाया जाता है। अब आप इस ज्ञान का उपयोग अपनी PDF फ़ाइलों में पारदर्शी रंगों के साथ ज्यामितीय आकृतियाँ बनाने के लिए कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य आपको .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ एक आयत बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। आप सीखेंगे कि अपनी PDF फ़ाइलों में पारदर्शी रंगों के साथ ज्यामितीय आकार कैसे जोड़ें।

#### प्रश्न: शुरू करने से पहले क्या पूर्व शर्तें आवश्यक हैं?

उत्तर: शुरू करने से पहले, सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और अपना डेवलपमेंट एनवायरनमेंट सेट कर लिया है। इसके अतिरिक्त, C# प्रोग्रामिंग की बुनियादी समझ होना अनुशंसित है।

#### प्रश्न: मैं पीडीएफ फाइल को सहेजने के लिए निर्देशिका कैसे निर्दिष्ट करूं?

उत्तर: उपलब्ध कराए गए स्रोत कोड में, आप "dataDir" वेरिएबल को संशोधित कर सकते हैं, ताकि वह डायरेक्टरी इंगित हो सके जहां आप परिणामी PDF फ़ाइल को सहेजना चाहते हैं।

#### प्रश्न: ग्राफ ऑब्जेक्ट और आयत का उद्देश्य क्या है?

उत्तर: ग्राफ ऑब्जेक्ट आरेखण तत्वों के लिए एक कंटेनर के रूप में कार्य करता है, जबकि आयत ज्यामितीय आकार का प्रतिनिधित्व करता है जिसे आप पीडीएफ में जोड़ेंगे।

#### प्रश्न: मैं आयत के लिए अल्फा रंग कैसे निर्धारित कर सकता हूँ?

 उत्तर: आप आयत के लिए अल्फा रंग निर्दिष्ट कर सकते हैं`FillColor` की संपत्ति`GraphInfo` वस्तु और`Color.FromRgb` ARGB मान वाली विधि।

#### प्रश्न: क्या मैं अलग-अलग अल्फा रंगों के साथ कई आयत बना सकता हूँ?

उत्तर: हां, आप ट्यूटोरियल में दिखाए गए समान चरणों का पालन करके विभिन्न अल्फा रंगों के साथ कई आयत बना सकते हैं।

#### प्रश्न: अल्फा रंगों के साथ आयत बनाने के बाद मैं परिणामी पीडीएफ फाइल को कैसे सेव करूँ?

 उत्तर: अल्फा रंगों के साथ आयत बनाने के बाद, आप परिणामी पीडीएफ फाइल को सेव कर सकते हैं`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` प्रदान किए गए स्रोत कोड में पंक्ति।