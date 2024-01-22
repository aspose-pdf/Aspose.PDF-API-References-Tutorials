---
title: पीडीएफ फाइल में कॉलम टेक्स्ट निकालें
linktitle: पीडीएफ फाइल में कॉलम टेक्स्ट निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कॉलम टेक्स्ट निकालना सीखें।
type: docs
weight: 150
url: /hi/net/programming-with-text/extract-columns-text/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में कॉलम टेक्स्ट निकालने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप कॉलम टेक्स्ट निकालना चाहते हैं, फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: पीडीएफ दस्तावेज़ खोलें
 का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ खोलें`Document`कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ पास करना।

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## चरण 5: फ़ॉन्ट आकार समायोजित करें
पठनीयता बढ़ाने और स्तंभ पाठ को बेहतर ढंग से प्रस्तुत करने के लिए पाठ के टुकड़ों के फ़ॉन्ट आकार को 0.7 गुना कम करें।

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## चरण 6: कॉलम से टेक्स्ट निकालें
 संशोधित पीडीएफ दस्तावेज़ को मेमोरी स्ट्रीम में सहेजें और इसे एक नए दस्तावेज़ के रूप में पुनः लोड करें। फिर, का उपयोग करें`TextAbsorber` कॉलम से टेक्स्ट निकालने के लिए क्लास।

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## चरण 7: निकाले गए टेक्स्ट को सहेजें
निकाले गए टेक्स्ट को निर्दिष्ट आउटपुट फ़ाइल पथ पर टेक्स्ट फ़ाइल में सहेजें।

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके कॉलम टेक्स्ट निकालने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// फ़ॉन्ट आकार को कम से कम 70% तक कम करने की आवश्यकता है
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से कॉलम टेक्स्ट को सफलतापूर्वक निकाला है। निकाले गए पाठ को निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: यह ट्यूटोरियल .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल से टेक्स्ट के कॉलम निकालने पर चरण-दर-चरण मार्गदर्शिका प्रदान करता है। संलग्न C# स्रोत कोड आवश्यक प्रक्रियाओं का व्यावहारिक प्रदर्शन प्रदान करता है।

#### प्रश्न: मुझे कौन से नामस्थान आयात करने चाहिए?

उ: कोड फ़ाइल में जहां आप टेक्स्ट के कॉलम निकालना चाहते हैं, फ़ाइल की शुरुआत में निर्देशों का उपयोग करते हुए निम्नलिखित शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` कोड में और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं मौजूदा पीडीएफ दस्तावेज़ कैसे खोलूं?

 उ: चरण 4 में, आप इसका उपयोग करके एक मौजूदा पीडीएफ दस्तावेज़ खोलेंगे`Document` कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ प्रदान करना।

#### प्रश्न: फ़ॉन्ट का आकार क्यों समायोजित किया जाता है?

उ: चरण 5 में पाठ अंशों के फ़ॉन्ट आकार को 0.7 गुना कम करना शामिल है। यह समायोजन पठनीयता को बढ़ाता है और स्तंभ पाठ को अधिक सटीक रूप से प्रस्तुत करता है।

#### प्रश्न: मैं कॉलम से टेक्स्ट कैसे निकालूं?

 उ: चरण 6 में संशोधित पीडीएफ दस्तावेज़ को मेमोरी स्ट्रीम में सहेजना, इसे एक नए दस्तावेज़ के रूप में पुनः लोड करना और फिर इसका उपयोग करना शामिल है`TextAbsorber` कॉलम से टेक्स्ट निकालने के लिए क्लास।

#### प्रश्न: निकाले गए पाठ को सहेजने का उद्देश्य क्या है?

उ: चरण 7 में, आप निकाले गए टेक्स्ट को निर्दिष्ट आउटपुट फ़ाइल पथ पर एक टेक्स्ट फ़ाइल में सहेजेंगे।

#### प्रश्न: निष्कर्षण से पहले फ़ॉन्ट का आकार क्यों कम करें?

उ: फ़ॉन्ट आकार को कम करने से यह सुनिश्चित करने में मदद मिलती है कि निकाला गया टेक्स्ट कॉलम के भीतर ठीक से संरेखित होता है, जिससे मूल लेआउट का अधिक सटीक प्रतिनिधित्व मिलता है।

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ से टेक्स्ट के कॉलम निकालने के लिए आवश्यक ज्ञान और कौशल हासिल कर लिया है। परिणामी पाठ को निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है।