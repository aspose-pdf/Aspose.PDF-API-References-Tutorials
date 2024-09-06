---
title: कॉलम टेक्स्ट को पीडीएफ फाइल में निकालें
linktitle: कॉलम टेक्स्ट को पीडीएफ फाइल में निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कॉलम टेक्स्ट निकालने का तरीका जानें।
type: docs
weight: 150
url: /hi/net/programming-with-text/extract-columns-text/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कॉलम टेक्स्ट निकालने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को प्रदर्शित करता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप कॉलम का पाठ निकालना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: पीडीएफ दस्तावेज़ खोलें
 किसी मौजूदा PDF दस्तावेज़ को खोलने के लिए निम्न का उपयोग करें:`Document` कन्स्ट्रक्टर का उपयोग करना और इनपुट पीडीएफ फाइल का पथ पास करना।

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## चरण 5: फ़ॉन्ट आकार समायोजित करें
पठनीयता बढ़ाने और स्तंभाकार पाठ को बेहतर ढंग से प्रस्तुत करने के लिए पाठ अंशों के फ़ॉन्ट आकार को 0.7 के कारक से कम करें।

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
 संशोधित PDF दस्तावेज़ को मेमोरी स्ट्रीम में सहेजें और इसे नए दस्तावेज़ के रूप में पुनः लोड करें। फिर, का उपयोग करें`TextAbsorber` कॉलम से पाठ निकालने के लिए क्लास।

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## चरण 7: निकाले गए पाठ को सहेजें
निकाले गए पाठ को निर्दिष्ट आउटपुट फ़ाइल पथ पर एक पाठ फ़ाइल में सहेजें।

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
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से कॉलम टेक्स्ट सफलतापूर्वक निकाला है। निकाला गया टेक्स्ट निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: यह ट्यूटोरियल .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल से टेक्स्ट के कॉलम निकालने पर चरण-दर-चरण मार्गदर्शन प्रदान करता है। साथ में दिया गया C# स्रोत कोड आवश्यक प्रक्रियाओं का व्यावहारिक प्रदर्शन प्रदान करता है।

#### प्रश्न: मुझे कौन से नामस्थान आयात करने चाहिए?

उत्तर: उस कोड फ़ाइल में जहाँ आप पाठ के कॉलम निकालना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित using निर्देश शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` कोड में और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं किसी मौजूदा पीडीएफ दस्तावेज़ को कैसे खोलूं?

 उत्तर: चरण 4 में, आप एक मौजूदा पीडीएफ दस्तावेज़ को खोलेंगे`Document` कंस्ट्रक्टर और इनपुट पीडीएफ फाइल के लिए पथ प्रदान करना।

#### प्रश्न: फ़ॉन्ट का आकार क्यों समायोजित किया जाता है?

उत्तर: चरण 5 में टेक्स्ट अंशों के फ़ॉन्ट आकार को 0.7 के कारक से कम करना शामिल है। यह समायोजन पठनीयता को बढ़ाता है और स्तंभीय पाठ को अधिक सटीकता से दर्शाता है।

#### प्रश्न: मैं कॉलम से टेक्स्ट कैसे निकालूं?

 उत्तर: चरण 6 में संशोधित पीडीएफ दस्तावेज़ को मेमोरी स्ट्रीम में सहेजना, उसे नए दस्तावेज़ के रूप में पुनः लोड करना और फिर उसका उपयोग करना शामिल है।`TextAbsorber` कॉलम से पाठ निकालने के लिए क्लास।

#### प्रश्न: निकाले गए पाठ को सहेजने का उद्देश्य क्या है?

उत्तर: चरण 7 में, आप निकाले गए पाठ को निर्दिष्ट आउटपुट फ़ाइल पथ पर एक पाठ फ़ाइल में सहेजेंगे।

#### प्रश्न: निष्कर्षण से पहले फ़ॉन्ट का आकार क्यों कम किया जाता है?

उत्तर: फ़ॉन्ट का आकार कम करने से यह सुनिश्चित करने में मदद मिलती है कि निकाला गया पाठ स्तंभों के भीतर ठीक से संरेखित हो, जिससे मूल लेआउट का अधिक सटीक प्रतिनिधित्व मिलता है।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से टेक्स्ट के कॉलम निकालने के लिए आवश्यक ज्ञान और कौशल प्राप्त कर लिया है। परिणामी टेक्स्ट को निर्दिष्ट आउटपुट फ़ाइल में सहेजा गया है।