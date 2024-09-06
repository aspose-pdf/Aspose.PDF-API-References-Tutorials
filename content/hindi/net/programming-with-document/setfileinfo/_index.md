---
title: पीडीएफ फाइल में फाइल जानकारी सेट करें
linktitle: पीडीएफ फाइल में फाइल जानकारी सेट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका के साथ PDF फ़ाइल में फ़ाइल जानकारी सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग करना सीखें।
type: docs
weight: 310
url: /hi/net/programming-with-document/setfileinfo/
---
यदि आप किसी ऐसे प्रोजेक्ट पर काम कर रहे हैं जिसमें .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइलों को प्रबंधित करने की आवश्यकता है, तो आप जिस सुविधा का उपयोग करना चाह सकते हैं, वह है PDF दस्तावेज़ के लिए फ़ाइल जानकारी सेट करने की क्षमता। फ़ाइल जानकारी में लेखक, निर्माण तिथि, कीवर्ड, संशोधन तिथि, विषय और शीर्षक जैसे विभिन्न विवरण शामिल हैं। यह मार्गदर्शिका आपको .NET के लिए Aspose.PDF के साथ C# स्रोत कोड का उपयोग करके PDF दस्तावेज़ के लिए फ़ाइल जानकारी सेट करने की प्रक्रिया से परिचित कराएगी।

## .NET के लिए Aspose.PDF का उपयोग करके फ़ाइल जानकारी सेट करने के लिए चरण-दर-चरण मार्गदर्शिका

1. अपने Visual Studio IDE में एक नया C# प्रोजेक्ट बनाएं।
2. अपने प्रोजेक्ट में Aspose.PDF for .NET लाइब्रेरी का संदर्भ जोड़ें।
3. उस PDF फ़ाइल का पथ प्रदान करके एक नया PDF दस्तावेज़ ऑब्जेक्ट बनाएं जिसके लिए आप फ़ाइल जानकारी संशोधित करना चाहते हैं।

## चरण 1: दस्तावेज़ निर्देशिका का पथ सेट करें।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ खोलें

```csharp
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## चरण 3: PDF दस्तावेज़ की फ़ाइल जानकारी तक पहुँचने के लिए DocumentInfo ऑब्जेक्ट का उपयोग करें।

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

## चरण 5: अद्यतन किए गए PDF दस्तावेज़ को निर्दिष्ट स्थान पर सहेजें।

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## चरण 6: सत्यापित करें कि फ़ाइल जानकारी सफलतापूर्वक अपडेट हो गई है।

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

निष्कर्ष में, Aspose.PDF for .NET PDF दस्तावेज़ों के लिए फ़ाइल जानकारी सेट करने का एक सरल और प्रभावी तरीका प्रदान करता है। ऊपर बताए गए चरणों का पालन करके, आप C# स्रोत कोड का उपयोग करके अपने PDF दस्तावेज़ों के लिए वांछित फ़ाइल जानकारी मान आसानी से सेट कर सकते हैं।

### पीडीएफ फाइल में फ़ाइल जानकारी सेट करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं उदाहरण में उल्लिखित न किए गए अतिरिक्त फ़ाइल जानकारी गुण सेट कर सकता हूँ?

 उत्तर: हां, आप इसका उपयोग करके अतिरिक्त फ़ाइल जानकारी गुण सेट कर सकते हैं`DocumentInfo` .NET के लिए Aspose.PDF में ऑब्जेक्ट।`DocumentInfo`क्लास विभिन्न गुण प्रदान करता है जो आपको निर्माता, संस्करण और कस्टम गुण जैसे अतिरिक्त जानकारी सेट करने की अनुमति देता है।

#### प्रश्न: क्या किसी मौजूदा पीडीएफ दस्तावेज़ से फ़ाइल जानकारी प्राप्त करना संभव है?

 उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके किसी मौजूदा PDF दस्तावेज़ से फ़ाइल जानकारी प्राप्त कर सकते हैं। ऐसा करने के लिए, आप इसका उपयोग कर सकते हैं`DocumentInfo` ऑब्जेक्ट का उपयोग फ़ाइल जानकारी गुणों तक पहुंचने और पीडीएफ दस्तावेज़ में संग्रहीत जानकारी को पढ़ने के लिए किया जाता है।

#### प्रश्न: क्या फ़ाइल जानकारी सेट करने से मूल PDF दस्तावेज़ संशोधित हो जाता है?

उत्तर: नहीं, .NET के लिए Aspose.PDF का उपयोग करके फ़ाइल जानकारी सेट करने से मूल PDF दस्तावेज़ में कोई बदलाव नहीं होता है। इसके बजाय, यह अपडेट की गई फ़ाइल जानकारी के साथ एक नया PDF दस्तावेज़ बनाता है। मूल PDF दस्तावेज़ अपरिवर्तित रहता है।