---
title: पीडीएफ गुण प्राप्त करें
linktitle: पीडीएफ गुण प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके बॉक्स आयाम और रोटेशन जैसी पीडीएफ गुण प्राप्त करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 100
url: /hi/net/programming-with-pdf-pages/get-properties/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ के गुण प्राप्त करने के लिए चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ पेज के विभिन्न गुणों जैसे आर्ट बॉक्स, क्रॉप बॉक्स, क्रॉप बॉक्स आदि तक कैसे पहुंचें।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान
- आपके विकास परिवेश में .NET के लिए Aspose.PDF स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह पीडीएफ फ़ाइल का स्थान है जिसके गुण आप प्राप्त करना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ खोलें
 इसके बाद, आपको इसका उपयोग करके पीडीएफ दस्तावेज़ को खोलना होगा`Document` Aspose.PDF की कक्षा। पीडीएफ फ़ाइल के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## चरण 3: पृष्ठ संग्रह तक पहुंचें
 अब आप इसका उपयोग करके दस्तावेज़ के पृष्ठों के संग्रह तक पहुंच सकते हैं`Pages` की संपत्ति`pdfDocument` वस्तु।

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## चरण 4: एक विशिष्ट पृष्ठ पर जाएँ
फिर आप संग्रह में पृष्ठ की अनुक्रमणिका का उपयोग करके किसी विशिष्ट पृष्ठ पर जा सकते हैं। नीचे दिए गए उदाहरण में, हम दूसरे पृष्ठ (सूचकांक 1) तक पहुंचते हैं।

```csharp
Page pdfPage = pageCollection[1];
```

## चरण 5: पृष्ठ गुण प्राप्त करें
 अब आप संबंधित गुणों का उपयोग करके पीडीएफ पेज के विभिन्न गुण, जैसे आर्ट बॉक्स, क्रॉप बॉक्स, क्रॉप बॉक्स इत्यादि प्राप्त कर सकते हैं।`pdfPage` वस्तु।

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### .NET के लिए Aspose.PDF का उपयोग करके गुण प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// पृष्ठ संग्रह प्राप्त करें
PageCollection pageCollection = pdfDocument.Pages;
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = pageCollection[1];
// पृष्ठ गुण प्राप्त करें
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF के गुण सफलतापूर्वक प्राप्त कर लिए हैं। आपने सीखा कि एक पीडीएफ दस्तावेज़ कैसे खोलें, एक विशिष्ट पृष्ठ पर नेविगेट करें और विभिन्न पृष्ठ गुण प्राप्त करें, जैसे आयाम बॉक्स और रोटेशन। अब आप इस जानकारी का उपयोग अपनी पीडीएफ फाइलों की हैंडलिंग को उनके गुणों के आधार पर अनुकूलित करने के लिए कर सकते हैं।

उन्नत सुविधाओं और अनुकूलन संभावनाओं पर अधिक जानकारी के लिए .NET दस्तावेज़ के लिए आधिकारिक Aspose.PDF को अवश्य देखें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ के गुण कैसे प्राप्त कर सकता हूं?

उ: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ के गुण प्राप्त करने के लिए, आप इन चरणों का पालन कर सकते हैं:

1. जिस पीडीएफ फ़ाइल के गुण आप पुनः प्राप्त करना चाहते हैं, उसका पथ निर्दिष्ट करके दस्तावेज़ निर्देशिका सेट करें।
2.  का उपयोग करके पीडीएफ दस्तावेज़ खोलें`Document` Aspose.PDF का वर्ग, पीडीएफ फ़ाइल को सही पथ प्रदान करता है।
3.  का उपयोग करके दस्तावेज़ के पृष्ठों के संग्रह तक पहुँचें`Pages` की संपत्ति`pdfDocument` वस्तु।
4. संग्रह में पृष्ठ की अनुक्रमणिका का उपयोग करके किसी विशिष्ट पृष्ठ पर जाएं (अनुक्रमणिका 1 से शुरू होती है)।
5.  संबंधित गुणों का उपयोग करके पीडीएफ पेज के विभिन्न गुण प्राप्त करें, जैसे कि आर्टबॉक्स, ब्लीडबॉक्स, क्रॉपबॉक्स, मीडियाबॉक्स, ट्रिमबॉक्स, रेक्ट, पेज नंबर और रोटेशन।`pdfPage` वस्तु।

#### प्रश्न: पीडीएफ पेज के विभिन्न गुण क्या हैं जिन्हें मैं .NET के लिए Aspose.PDF का उपयोग करके पुनः प्राप्त कर सकता हूं?

उ: आप .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ पेज के विभिन्न गुणों को पुनः प्राप्त कर सकते हैं, जैसे:

- आर्टबॉक्स: पृष्ठ की कलाकृति के आयामों का प्रतिनिधित्व करता है।
- ब्लीडबॉक्स: पृष्ठ के ब्लीड के आयामों का प्रतिनिधित्व करता है।
- क्रॉपबॉक्स: क्रॉप करने के बाद पृष्ठ की दृश्यमान सामग्री के आयामों का प्रतिनिधित्व करता है।
- मीडियाबॉक्स: पृष्ठ के भौतिक मीडिया के आयामों का प्रतिनिधित्व करता है।
- ट्रिमबॉक्स: पृष्ठ की छंटनी की गई सामग्री के आयामों का प्रतिनिधित्व करता है।
- Rect: पृष्ठ के बाउंडिंग बॉक्स के आयामों का प्रतिनिधित्व करता है।
- पृष्ठ संख्या: दस्तावेज़ में पृष्ठ संख्या का प्रतिनिधित्व करता है।
- घुमाएँ: पृष्ठ के घूर्णन कोण का प्रतिनिधित्व करता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में किसी विशिष्ट पृष्ठ तक उसकी संपत्तियों को पुनः प्राप्त करने के लिए कैसे पहुंच सकता हूं?

 उ: पीडीएफ दस्तावेज़ में किसी विशिष्ट पृष्ठ तक पहुंचने और उसके गुणों को पुनः प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`Pages` की संपत्ति`pdfDocument` दस्तावेज़ के पृष्ठों के संग्रह तक पहुँचने के लिए ऑब्जेक्ट। फिर, आप वांछित पृष्ठ पर जाने के लिए संग्रह में पृष्ठ की अनुक्रमणिका का उपयोग कर सकते हैं। उदाहरण के लिए, दूसरे पृष्ठ तक पहुँचने के लिए, आप इसका उपयोग कर सकते हैं`pdfDocument.Pages[1]` (अनुक्रमण 1 से प्रारंभ होता है)।

#### प्रश्न: क्या मैं पुनर्प्राप्त संपत्तियों पर संचालन कर सकता हूं, जैसे पेज बॉक्स को संशोधित करना या आकार बदलना?

उ: हां, एक बार जब आप .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ पेज के गुणों को पुनः प्राप्त कर लेते हैं, तो आप उन पर विभिन्न ऑपरेशन कर सकते हैं। उदाहरण के लिए, आप पेज बॉक्स के आयामों को संशोधित कर सकते हैं, पेज को घुमा सकते हैं, या पीडीएफ दस्तावेज़ के कस्टम प्रसंस्करण और हेरफेर के लिए पुनर्प्राप्त जानकारी का उपयोग कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF एन्क्रिप्टेड या पासवर्ड-संरक्षित पीडीएफ फाइलों से गुण निकालने का समर्थन करता है?

उत्तर: हां, .NET के लिए Aspose.PDF एन्क्रिप्टेड या पासवर्ड-संरक्षित पीडीएफ फाइलों से गुण निकालने का समर्थन करता है। जब तक आप पीडीएफ दस्तावेज़ को खोलने के लिए सही पासवर्ड प्रदान करते हैं, तब तक आप ट्यूटोरियल में दिखाए गए समान दृष्टिकोण का उपयोग करके इसके गुणों तक पहुंच सकते हैं और पुनः प्राप्त कर सकते हैं।