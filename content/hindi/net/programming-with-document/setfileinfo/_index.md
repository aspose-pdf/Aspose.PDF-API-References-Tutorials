---
title: फ़ाइल जानकारी को पीडीएफ फ़ाइल में सेट करें
linktitle: फ़ाइल जानकारी को पीडीएफ फ़ाइल में सेट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका से पीडीएफ फ़ाइल में फ़ाइल जानकारी सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग करना सीखें।
type: docs
weight: 310
url: /hi/net/programming-with-document/setfileinfo/
---
यदि आप एक ऐसे प्रोजेक्ट पर काम कर रहे हैं जिसके लिए .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइलों को प्रबंधित करने की आवश्यकता है, तो जिन सुविधाओं का आप उपयोग करना चाहते हैं उनमें से एक पीडीएफ दस्तावेज़ के लिए फ़ाइल जानकारी सेट करने की क्षमता है। फ़ाइल जानकारी में लेखक, निर्माण तिथि, कीवर्ड, संशोधन तिथि, विषय और शीर्षक जैसे विभिन्न विवरण शामिल हैं। यह मार्गदर्शिका आपको .NET के लिए Aspose.PDF के साथ C# स्रोत कोड का उपयोग करके एक PDF दस्तावेज़ के लिए फ़ाइल जानकारी सेट करने की प्रक्रिया के बारे में बताएगी।

## .NET के लिए Aspose.PDF का उपयोग करके फ़ाइल जानकारी सेट करने के लिए चरण-दर-चरण मार्गदर्शिका

1. अपने विज़ुअल स्टूडियो IDE में एक नया C# प्रोजेक्ट बनाएं।
2. अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।
3. जिस पीडीएफ फ़ाइल के लिए आप फ़ाइल जानकारी को संशोधित करना चाहते हैं, उसके लिए पथ प्रदान करके एक नया पीडीएफ दस्तावेज़ ऑब्जेक्ट बनाएं।

## चरण 1: दस्तावेज़ निर्देशिका के लिए पथ सेट करें।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ खोलें

```csharp
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## चरण 3: पीडीएफ दस्तावेज़ की फ़ाइल जानकारी तक पहुंचने के लिए DocumentInfo ऑब्जेक्ट का उपयोग करें।

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## चरण 4: DocumentInfo ऑब्जेक्ट के गुणों का उपयोग करके वांछित फ़ाइल जानकारी मान सेट करें।

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## चरण 5: अद्यतन पीडीएफ दस्तावेज़ को निर्दिष्ट स्थान पर सहेजें।

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## चरण 6: सत्यापित करें कि फ़ाइल जानकारी सफलतापूर्वक अपडेट कर दी गई है।

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के लिए फ़ाइल जानकारी सफलतापूर्वक सेट कर ली है।

### .NET के लिए Aspose.PDF का उपयोग करके फ़ाइल जानकारी सेट करने के लिए उदाहरण स्रोत कोड


```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// दस्तावेज़ जानकारी निर्दिष्ट करें
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// आउटपुट दस्तावेज़ सहेजें
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष

अंत में, .NET के लिए Aspose.PDF PDF दस्तावेज़ों के लिए फ़ाइल जानकारी सेट करने का एक सरल और प्रभावी तरीका प्रदान करता है। उपर्युक्त चरणों का पालन करके, आप C# स्रोत कोड का उपयोग करके अपने पीडीएफ दस्तावेज़ों के लिए वांछित फ़ाइल जानकारी मान आसानी से सेट कर सकते हैं।

### पीडीएफ फ़ाइल में सेट फ़ाइल जानकारी के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं अतिरिक्त फ़ाइल सूचना गुण सेट कर सकता हूँ जिनका उदाहरण में उल्लेख नहीं किया गया है?

 उत्तर: हाँ, आप इसका उपयोग करके अतिरिक्त फ़ाइल सूचना गुण सेट कर सकते हैं`DocumentInfo` .NET के लिए Aspose.PDF में ऑब्जेक्ट।`DocumentInfo`क्लास विभिन्न गुण प्रदान करता है जो आपको अतिरिक्त जानकारी जैसे निर्माता, संस्करण और कस्टम गुण सेट करने की अनुमति देता है।

#### प्रश्न: क्या किसी मौजूदा पीडीएफ दस्तावेज़ से फ़ाइल जानकारी पुनर्प्राप्त करना संभव है?

 उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ से फ़ाइल जानकारी पुनर्प्राप्त कर सकते हैं। ऐसा करने के लिए, आप इसका उपयोग कर सकते हैं`DocumentInfo` फ़ाइल सूचना गुणों तक पहुँचने और पीडीएफ दस्तावेज़ में संग्रहीत जानकारी को पढ़ने के लिए ऑब्जेक्ट का उपयोग करें।

#### प्रश्न: क्या फ़ाइल जानकारी सेट करने से मूल पीडीएफ दस्तावेज़ संशोधित हो जाता है?

उ: नहीं, .NET के लिए Aspose.PDF का उपयोग करके फ़ाइल जानकारी सेट करने से मूल PDF दस्तावेज़ संशोधित नहीं होता है। इसके बजाय, यह अद्यतन फ़ाइल जानकारी के साथ एक नया पीडीएफ दस्तावेज़ बनाता है। मूल पीडीएफ दस्तावेज़ अपरिवर्तित रहता है।