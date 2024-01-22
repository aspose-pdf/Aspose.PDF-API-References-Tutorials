---
title: एनोटेशन का संसाधन प्राप्त करें
linktitle: एनोटेशन का संसाधन प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका से जानें कि .NET के लिए Aspose.PDF का उपयोग करके एनोटेशन के संसाधन को कैसे पुनः प्राप्त किया जाए।
type: docs
weight: 90
url: /hi/net/annotations/getresourceofannotation/
---
उदाहरण दिखाता है कि .NET के लिए Aspose.PDF के साथ एनोटेशन का संसाधन कैसे प्राप्त करें। .NET के लिए Aspose.PDF का उपयोग करके एनोटेशन का संसाधन प्राप्त करने के लिए, इन चरणों का पालन करें:

## चरण 1: उस निर्देशिका का पथ सेट करें जहां दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ खोलें जिसमें वह एनोटेशन है जिसका संसाधन आप प्राप्त करना चाहते हैं।

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## चरण 3: एक एनोटेशन बनाएं.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## चरण 4: दस्तावेज़ में एक पृष्ठ पर एनोटेशन जोड़ें।

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## चरण 5: दस्तावेज़ सहेजें।

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## चरण 6: संशोधित दस्तावेज़ खोलें।

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## चरण 7: एनोटेशन की कार्रवाई प्राप्त करें।

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## चरण 7: कार्रवाई का प्रतिपादन प्राप्त करें।

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## चरण 8: मीडिया क्लिप प्राप्त करें।

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## चरण 9: फ़ाइल विनिर्देश प्राप्त करें।

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## चरण 10: मीडिया का डेटा पढ़ें।

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## चरण 11: प्रस्तुतिकरण और प्रस्तुतिकरण ऑपरेशन का नाम प्रिंट करें।

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

इन चरणों का पालन करके, आप .NET के लिए Aspose.PDF का उपयोग करके आसानी से एक पीडीएफ दस्तावेज़ में एनोटेशन का संसाधन प्राप्त कर सकते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके एनोटेशन का संसाधन प्राप्त करने के लिए उदाहरण स्रोत कोड:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//एनोटेशन बनाएं
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// दस्तावेज़ सहेजें
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// दस्तावेज़ खोलें
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//एनोटेशन की कार्रवाई प्राप्त करें
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//प्रतिपादन क्रिया का प्रतिपादन प्राप्त करें
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// मीडिया क्लिप
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//मीडिया का डेटा FileSpecification.Contents में पहुंच योग्य है
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ से किसी विशेष एनोटेशन का संसाधन कैसे प्राप्त किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, डेवलपर्स अपने पीडीएफ दस्तावेज़ों में रेंडरिशन एनोटेशन सहित एनोटेशन तक आसानी से पहुंच और प्रबंधन कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ एनोटेशन के संदर्भ में प्रस्तुतिकरण क्या है?

उत्तर: पीडीएफ एनोटेशन के संदर्भ में, प्रस्तुति एक मल्टीमीडिया सामग्री प्रस्तुति है। यह पीडीएफ दस्तावेज़ के भीतर ऑडियो या वीडियो जैसे मल्टीमीडिया को एम्बेड करने की अनुमति देता है। प्रस्तुति एनोटेशन प्रस्तुत किए जाने वाले मीडिया को निर्दिष्ट करता है और इसे कैसे चलाया जाना चाहिए।

#### प्रश्न: क्या मुझे रेंडरिशन एनोटेशन से जुड़ी मीडिया फ़ाइल का नाम मिल सकता है?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके रेंडरिशन एनोटेशन से जुड़ी मीडिया फ़ाइल का नाम प्राप्त कर सकते हैं। मीडिया फ़ाइल नाम को इसके माध्यम से एक्सेस किया जा सकता है`FileSpecification` की`MediaClip` वस्तु।

#### प्रश्न: क्या .NET के लिए Aspose.PDF रेंडरिशन एनोटेशन से मीडिया फ़ाइलें निकाल सकता है?

उ: हाँ, .NET के लिए Aspose.PDF एक रेंडरिशन एनोटेशन से मीडिया डेटा निकाल सकता है, जिसमें ऑडियो या वीडियो सामग्री शामिल है, और इसे एक अलग फ़ाइल के रूप में सहेज सकता है।

#### प्रश्न: मैं रेंडरिशन एनोटेशन के मीडिया डेटा तक कैसे पहुंच सकता हूं?

 ए: रेंडरिशन एनोटेशन के मीडिया डेटा को इसके माध्यम से एक्सेस किया जा सकता है`FileSpecification.Contents` की संपत्ति`MediaClipData` वस्तु।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके रेंडरिशन एनोटेशन से जुड़े मीडिया को संशोधित कर सकता हूं?

उत्तर: .NET के लिए Aspose.PDF एक रेंडरिशन एनोटेशन से जुड़े मीडिया डेटा तक पहुंचने और संशोधित करने के तरीके प्रदान करता है। आप रेंडरिशन एनोटेशन द्वारा उपयोग की गई मीडिया फ़ाइल को अपडेट या प्रतिस्थापित कर सकते हैं।