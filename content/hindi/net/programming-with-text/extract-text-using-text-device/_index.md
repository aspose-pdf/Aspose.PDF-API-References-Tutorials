---
title: टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालें
linktitle: टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस का उपयोग करके PDF दस्तावेज़ से टेक्स्ट निकालना सीखें।
type: docs
weight: 210
url: /hi/net/programming-with-text/extract-text-using-text-device/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस का उपयोग करके PDF दस्तावेज़ से टेक्स्ट निकालने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ से आप पाठ निकालना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: पीडीएफ दस्तावेज़ खोलें
 किसी मौजूदा PDF दस्तावेज़ को खोलने के लिए निम्न का उपयोग करें:`Document` कन्स्ट्रक्टर का उपयोग करना और इनपुट पीडीएफ फाइल का पथ पास करना।

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## चरण 5: टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट निकालें
 एक बनाने के`StringBuilder` निकाले गए टेक्स्ट को रखने के लिए ऑब्जेक्ट। दस्तावेज़ के प्रत्येक पृष्ठ पर पुनरावृत्ति करें और एक का उपयोग करें`TextDevice` प्रत्येक पृष्ठ से पाठ निकालने के लिए.

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

## चरण 6: निकाले गए पाठ को सहेजें
 आउटपुट फ़ाइल पथ निर्दिष्ट करें और निकाले गए पाठ को टेक्स्ट फ़ाइल में सहेजें`File.WriteAllText` तरीका।

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
		// पाठ निष्कर्षण विकल्प सेट करें - पाठ निष्कर्षण मोड सेट करें (कच्चा या शुद्ध)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// किसी विशेष पृष्ठ को रूपांतरित करें और पाठ को स्ट्रीम में सहेजें
		textDevice.Process(pdfPage, textStream);
		// किसी विशेष पृष्ठ को रूपांतरित करें और पाठ को स्ट्रीम में सहेजें
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// मेमोरी स्ट्रीम बंद करें
		textStream.Close();
		// मेमोरी स्ट्रीम से पाठ प्राप्त करें
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// निकाले गए पाठ को टेक्स्ट फ़ाइल में सहेजें
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस का उपयोग करके PDF दस्तावेज़ से सफलतापूर्वक टेक्स्ट निकाला है। निकाला गया टेक्स्ट निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: यह ट्यूटोरियल .NET के लिए Aspose.PDF में टेक्स्ट डिवाइस सुविधा का उपयोग करके PDF दस्तावेज़ से टेक्स्ट निकालने पर मार्गदर्शन प्रदान करता है। साथ में दिया गया C# स्रोत कोड इस कार्य को पूरा करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: मुझे कौन से नामस्थान आयात करने चाहिए?

उत्तर: जिस कोड फ़ाइल में आप पाठ निकालने की योजना बना रहे हैं, फ़ाइल के आरंभ में निम्नलिखित using निर्देश शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में वह पंक्ति ढूंढें जिसमें लिखा हो`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं किसी मौजूदा पीडीएफ दस्तावेज़ को कैसे खोलूं?

 उत्तर: चरण 4 में, आप एक मौजूदा पीडीएफ दस्तावेज़ को खोलेंगे`Document` कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ प्रदान करना।

#### प्रश्न: मैं टेक्स्ट डिवाइस का उपयोग करके टेक्स्ट कैसे निकालूं?

 उत्तर: चरण 5 में एक बनाना शामिल है`StringBuilder` निकाले गए टेक्स्ट को रखने के लिए ऑब्जेक्ट। फिर आप दस्तावेज़ के प्रत्येक पृष्ठ पर पुनरावृत्ति करेंगे और एक का उपयोग करेंगे`TextDevice` साथ में`TextExtractionOptions` प्रत्येक पृष्ठ से पाठ निकालने के लिए.

#### प्रश्न: मैं निकाले गए पाठ को फ़ाइल में कैसे सहेजूँ?

 उत्तर: चरण 6 में, आप आउटपुट फ़ाइल पथ निर्दिष्ट करेंगे और इसका उपयोग करेंगे`File.WriteAllText`निकाले गए पाठ को पाठ फ़ाइल में सहेजने की विधि।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि PDF दस्तावेज़ से टेक्स्ट निकालने के लिए Aspose.PDF for .NET में टेक्स्ट डिवाइस सुविधा का लाभ कैसे उठाया जाए। निकाले गए टेक्स्ट को एक निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है, जिससे आप आवश्यकतानुसार निकाले गए कंटेंट में हेरफेर और उसका उपयोग कर सकते हैं।