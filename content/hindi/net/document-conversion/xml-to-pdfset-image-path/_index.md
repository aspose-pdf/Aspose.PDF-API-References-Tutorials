---
title: XML से PDFसेट छवि पथ
linktitle: XML से PDFसेट छवि पथ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ XML को PDF में कनवर्ट करते समय छवि का पथ सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 340
url: /hi/net/document-conversion/xml-to-pdfset-image-path/
---
इस ट्यूटोरियल में, हम आपको चरण-दर-चरण बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके XML फ़ाइल को पीडीएफ में परिवर्तित करते समय छवि का पथ कैसे सेट किया जाए। हम दिए गए C# स्रोत कोड के बारे में विस्तार से बताएंगे और आपको दिखाएंगे कि इसे अपनी परियोजनाओं में कैसे लागू किया जाए। इस ट्यूटोरियल के अंत तक, आप XML को पीडीएफ में परिवर्तित करते समय आसानी से एक छवि का पथ निर्दिष्ट कर सकते हैं।

## चरण 1: फ़ाइल पथ सेट करें
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 इनपुट XML फ़ाइलों के पथ, उपयोग की जाने वाली छवि और आउटपुट PDF फ़ाइल को परिभाषित करें। प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` उस पथ के साथ जहां आपने अपनी फ़ाइलें सहेजी थीं।

## चरण 2: दस्तावेज़ ऑब्जेक्ट को त्वरित करें
```csharp
Document doc = new Document();
```
दस्तावेज़ ऑब्जेक्ट का एक उदाहरण बनाएँ।

## चरण 3: स्रोत XML फ़ाइल को लिंक करें
```csharp
doc. BindXml(inXml);
```
स्रोत XML फ़ाइल को दस्तावेज़ से लिंक करता है।

## चरण 4: छवि पथ सेट करें
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
XML की आईडी का उपयोग करके उससे छवि ऑब्जेक्ट संदर्भ प्राप्त करें और उपयोग के लिए छवि का पथ निर्धारित करें।

## चरण 5: परिणामी पीडीएफ फाइल को सहेजें
```csharp
doc.Save(outFile);
```
परिणामी पीडीएफ फाइल को निर्दिष्ट निर्देशिका में सहेजें।

### .NET के लिए Aspose.PDF का उपयोग करके XML से PDFSet छवि पथ के लिए उदाहरण स्रोत कोड

```csharp
try
{
	
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके XML को PDF में कनवर्ट करते समय एक छवि का पथ कैसे सेट किया जाए। दिए गए चरणों का पालन करके, आप आसानी से अपने XML से PDF रूपांतरण में छवि पथ निर्दिष्ट कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: XML को PDF में परिवर्तित करते समय छवि पथ सेट करने का उद्देश्य क्या है?

उ: XML को पीडीएफ में परिवर्तित करते समय, छवि पथ सेट करने से आप XML में संदर्भित छवि का स्थान निर्दिष्ट कर सकते हैं। यह सुनिश्चित करता है कि छवि परिणामी पीडीएफ दस्तावेज़ में सही ढंग से प्रदर्शित है।

#### प्रश्न: क्या मैं विभिन्न निर्देशिकाओं से छवियों का उपयोग कर सकता हूँ?

 उत्तर: हाँ, आप प्रत्येक छवि के लिए सही फ़ाइल पथ प्रदान करके विभिन्न निर्देशिकाओं से छवियों का उपयोग कर सकते हैं। दिए गए कोड में,`inFile` वेरिएबल छवि फ़ाइल का पथ रखता है, और आप इसे विभिन्न निर्देशिकाओं में छवियों को इंगित करने के लिए अपडेट कर सकते हैं।

#### प्रश्न: क्या मैं किसी दूरस्थ URL से छवियों का उपयोग कर सकता हूँ?

उ: हां, आप स्थानीय फ़ाइल पथ के बजाय यूआरएल प्रदान करके दूरस्थ यूआरएल से छवियों का उपयोग कर सकते हैं। सुनिश्चित करें कि आपके एप्लिकेशन के पास दूरस्थ URL से छवि पुनर्प्राप्त करने के लिए इंटरनेट पहुंच है।

#### प्रश्न: इनपुट XML फ़ाइल का प्रारूप क्या होना चाहिए?

ए: इनपुट एक्सएमएल फ़ाइल में एक संरचना होनी चाहिए जो आईडी का उपयोग करके छवि को संदर्भित करती है। दिए गए कोड में, छवि को संदर्भित करने के लिए आईडी "testImg" का उपयोग किया जाता है।

#### प्रश्न: क्या मैं पीडीएफ में एकाधिक छवियां जोड़ सकता हूं?

उत्तर: हां, आप अलग-अलग आईडी का उपयोग करके XML फ़ाइल में उन्हें संदर्भित करके और तदनुसार फ़ाइल पथ सेट करके पीडीएफ में कई छवियां जोड़ सकते हैं।