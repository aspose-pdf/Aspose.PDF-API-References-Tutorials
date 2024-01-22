---
title: अल्फा रंग से आयत बनाएं
linktitle: अल्फा रंग से आयत बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पारदर्शी रंग के साथ एक आयत बनाना सीखें। पारदर्शिता को अनुकूलित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 60
url: /hi/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ एक आयत बनाने के लिए चरण दर चरण निम्नलिखित C# स्रोत कोड के बारे में बताएंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना विकास वातावरण स्थापित कर लिया है। C# प्रोग्रामिंग का बुनियादी ज्ञान भी हो।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए स्रोत कोड में, आपको वह निर्देशिका निर्दिष्ट करनी होगी जहां आप परिणामी पीडीएफ फ़ाइल को सहेजना चाहते हैं। "डेटाडिर" वेरिएबल को वांछित निर्देशिका में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक दस्तावेज़ ऑब्जेक्ट को इंस्टेंट करना और एक पेज जोड़ना

हम दस्तावेज़ वर्ग का एक उदाहरण बनाते हैं और इस दस्तावेज़ में एक पृष्ठ जोड़ते हैं।

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## चरण 3: एक ग्राफ़ ऑब्जेक्ट और एक आयत बनाना

हम निर्दिष्ट आयामों के साथ एक ग्राफ़ ऑब्जेक्ट और विशिष्ट आयामों के साथ एक आयत बनाते हैं।

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## चरण 4: आयत के लिए अल्फ़ा रंग सेट करना

हम System.Drawing.Color वर्ग की FromArgb विधि का उपयोग करके आयत के लिए एक अल्फा रंग निर्दिष्ट कर सकते हैं।

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## चरण 5: आयत को ग्राफ़ ऑब्जेक्ट में जोड़ना

हम आयत को ग्राफ़ ऑब्जेक्ट के आकार संग्रह में जोड़ते हैं।

```csharp
canvas.Shapes.Add(rect);
```

## चरण 6: भिन्न अल्फ़ा रंग के साथ दूसरा आयत बनाना

हम विशिष्ट आयामों और एक अन्य अल्फा रंग के साथ एक दूसरा आयत बनाते हैं।

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## चरण 7: पृष्ठ पर ग्राफ़ ऑब्जेक्ट जोड़ना

हम ग्राफ़ ऑब्जेक्ट को पेज ऑब्जेक्ट के पैराग्राफ़ संग्रह में जोड़ते हैं।

```csharp
page.Paragraphs.Add(canvas);
```

## चरण 8: परिणामी पीडीएफ फाइल को सहेजना

अंत में, हम परिणामी पीडीएफ फाइल को निर्दिष्ट निर्देशिका में "CreateRectangelWithAlphaColor_out.pdf" नाम से सहेजते हैं।

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ आयत बनाने के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// त्वरित दस्तावेज़ उदाहरण
Document doc = new Document();
// पीडीएफ फाइल के पेज संग्रह में पेज जोड़ें
Aspose.Pdf.Page page = doc.Pages.Add();
// ग्राफ़ उदाहरण बनाएँ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// विशिष्ट आयामों के साथ आयताकार वस्तु बनाएं
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//32-बिट ARGB मान से System.Drawing.Color संरचना से ग्राफ़ भरण रंग सेट करें
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// ग्राफ़ उदाहरण के आकार संग्रह में आयताकार ऑब्जेक्ट जोड़ें
canvas.Shapes.Add(rect);
// दूसरी आयत वस्तु बनाएँ
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// पेज ऑब्जेक्ट के पैराग्राफ संग्रह में ग्राफ़ इंस्टेंस जोड़ें
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// पीडीएफ फाइल सेव करें
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने बताया कि .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ एक आयत कैसे बनाया जाए। अब आप इस ज्ञान का उपयोग अपनी पीडीएफ फाइलों में पारदर्शी रंगों के साथ ज्यामितीय आकृतियाँ बनाने के लिए कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य .NET के लिए Aspose.PDF का उपयोग करके अल्फा रंग के साथ एक आयत बनाने की प्रक्रिया में आपका मार्गदर्शन करना है। आप सीखेंगे कि अपनी पीडीएफ फाइलों में पारदर्शी रंगों के साथ ज्यामितीय आकृतियाँ कैसे जोड़ें।

#### प्रश्न: शुरू करने से पहले क्या आवश्यक शर्तें आवश्यक हैं?

उ: शुरू करने से पहले, सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और अपना विकास वातावरण स्थापित कर लिया है। इसके अतिरिक्त, C# प्रोग्रामिंग की बुनियादी समझ रखने की अनुशंसा की जाती है।

#### प्रश्न: मैं पीडीएफ फ़ाइल को सहेजने के लिए निर्देशिका कैसे निर्दिष्ट करूं?

उ: दिए गए स्रोत कोड में, आप उस निर्देशिका को इंगित करने के लिए "डेटाडिर" वेरिएबल को संशोधित कर सकते हैं जहां आप परिणामी पीडीएफ फाइल को सहेजना चाहते हैं।

#### प्रश्न: ग्राफ़ ऑब्जेक्ट और रेक्टेंगल का उद्देश्य क्या है?

उ: ग्राफ़ ऑब्जेक्ट ड्राइंग तत्वों के लिए एक कंटेनर के रूप में कार्य करता है, जबकि आयत उस ज्यामितीय आकार का प्रतिनिधित्व करता है जिसे आप पीडीएफ में जोड़ रहे होंगे।

#### प्रश्न: मैं आयत के लिए अल्फ़ा रंग कैसे सेट कर सकता हूँ?

उ: आप इसका उपयोग करके आयत के लिए एक अल्फा रंग निर्दिष्ट कर सकते हैं`FillColor` की संपत्ति`GraphInfo` वस्तु और`Color.FromRgb` ARGB मान वाली विधि।

#### प्रश्न: क्या मैं विभिन्न अल्फ़ा रंगों के साथ अनेक आयत बना सकता हूँ?

उ: हां, आप ट्यूटोरियल में दिखाए गए समान चरणों का पालन करके विभिन्न अल्फा रंगों के साथ कई आयत बना सकते हैं।

#### प्रश्न: अल्फा रंगों के साथ आयत बनाने के बाद मैं परिणामी पीडीएफ फाइल को कैसे सहेज सकता हूं?

 उ: अल्फा रंगों के साथ आयत बनाने के बाद, आप परिणामी पीडीएफ फाइल को इसका उपयोग करके सहेज सकते हैं`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` दिए गए स्रोत कोड में पंक्ति।