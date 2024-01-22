---
title: टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालें
linktitle: टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस का उपयोग करके PDF दस्तावेज़ से टेक्स्ट निकालने का तरीका जानें।
type: docs
weight: 210
url: /hi/net/programming-with-text/extract-text-using-text-device/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस का उपयोग करके एक पीडीएफ दस्तावेज़ से टेक्स्ट निकालने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप टेक्स्ट निकालना चाहते हैं, फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: पीडीएफ दस्तावेज़ खोलें
 का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ खोलें`Document`कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ पास करना।

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## चरण 5: टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालें
 एक बनाने के`StringBuilder` निकाले गए पाठ को रखने के लिए ऑब्जेक्ट। दस्तावेज़ के प्रत्येक पृष्ठ को दोहराएँ और a का उपयोग करें`TextDevice` प्रत्येक पृष्ठ से पाठ निकालने के लिए।

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## चरण 6: निकाले गए टेक्स्ट को सहेजें
 आउटपुट फ़ाइल पथ निर्दिष्ट करें और निकाले गए टेक्स्ट को टेक्स्ट फ़ाइल में सहेजें`File.WriteAllText` तरीका।

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//निकाले गए पाठ को रखने के लिए स्ट्रिंग
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// टेक्स्ट डिवाइस बनाएं
		TextDevice textDevice = new TextDevice();
		// टेक्स्ट निष्कर्षण विकल्प सेट करें - टेक्स्ट निष्कर्षण मोड सेट करें (कच्चा या शुद्ध)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// किसी विशेष पृष्ठ को कनवर्ट करें और टेक्स्ट को स्ट्रीम में सहेजें
		textDevice.Process(pdfPage, textStream);
		// किसी विशेष पृष्ठ को कनवर्ट करें और टेक्स्ट को स्ट्रीम में सहेजें
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// मेमोरी स्ट्रीम बंद करें
		textStream.Close();
		// मेमोरी स्ट्रीम से टेक्स्ट प्राप्त करें
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// निकाले गए टेक्स्ट को टेक्स्ट फ़ाइल में सेव करें
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस का उपयोग करके PDF दस्तावेज़ से टेक्स्ट को सफलतापूर्वक निकाला है। निकाले गए पाठ को निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उ: यह ट्यूटोरियल .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस सुविधा का उपयोग करके पीडीएफ दस्तावेज़ से टेक्स्ट निकालने पर मार्गदर्शन प्रदान करता है। संलग्न C# स्रोत कोड इस कार्य को प्राप्त करने के लिए आवश्यक चरणों को दर्शाता है।

#### प्रश्न: मुझे कौन से नामस्थान आयात करने चाहिए?

ए: कोड फ़ाइल में जहां आप टेक्स्ट निकालने की योजना बना रहे हैं, फ़ाइल की शुरुआत में निर्देशों का उपयोग करके निम्नलिखित शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 उ: कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं मौजूदा पीडीएफ दस्तावेज़ कैसे खोलूं?

 उ: चरण 4 में, आप इसका उपयोग करके एक मौजूदा पीडीएफ दस्तावेज़ खोलेंगे`Document` कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ प्रदान करना।

#### प्रश्न: मैं टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट कैसे निकालूं?

 ए: चरण 5 में ए बनाना शामिल है`StringBuilder` निकाले गए पाठ को रखने के लिए ऑब्जेक्ट। फिर आप दस्तावेज़ के प्रत्येक पृष्ठ को दोहराएँगे और a का उपयोग करेंगे`TextDevice` साथ में`TextExtractionOptions` प्रत्येक पृष्ठ से पाठ निकालने के लिए.

#### प्रश्न: मैं निकाले गए टेक्स्ट को फ़ाइल में कैसे सहेजूँ?

 उ: चरण 6 में, आप आउटपुट फ़ाइल पथ निर्दिष्ट करेंगे और इसका उपयोग करेंगे`File.WriteAllText`निकाले गए टेक्स्ट को टेक्स्ट फ़ाइल में सहेजने की विधि।

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि पीडीएफ दस्तावेज़ से टेक्स्ट निकालने के लिए .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस सुविधा का लाभ कैसे उठाया जाए। निकाले गए पाठ को एक निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है, जिससे आप आवश्यकतानुसार निकाली गई सामग्री में हेरफेर और उपयोग कर सकते हैं।