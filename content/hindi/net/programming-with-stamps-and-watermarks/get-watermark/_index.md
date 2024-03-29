---
title: पीडीएफ फाइल से वॉटरमार्क प्राप्त करें
linktitle: पीडीएफ फाइल से वॉटरमार्क प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ PDF फ़ाइल से वॉटरमार्क निकालने का तरीका जानें।
type: docs
weight: 100
url: /hi/net/programming-with-stamps-and-watermarks/get-watermark/
---
इस ट्यूटोरियल में, हम आपको चरण दर चरण बताएंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल से वॉटरमार्क कैसे प्राप्त करें। हम आपको दिखाएंगे कि किसी विशिष्ट पृष्ठ की कलाकृतियों के माध्यम से पुनरावृति करने और वॉटरमार्क प्रकार, पाठ और स्थान प्राप्त करने के लिए दिए गए C# स्रोत कोड का उपयोग कैसे करें।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- एक स्थापित .NET विकास वातावरण।
- .NET के लिए Aspose.PDF लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में संदर्भित की गई।

## चरण 2: पीडीएफ दस्तावेज़ लोड हो रहा है

पहला कदम मौजूदा पीडीएफ दस्तावेज़ को अपने प्रोजेक्ट में लोड करना है। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//पीडीएफ दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

"आपकी दस्तावेज़ निर्देशिका" को उस निर्देशिका के वास्तविक पथ से बदलना सुनिश्चित करें जहां आपका पीडीएफ दस्तावेज़ स्थित है।

## चरण 3: वॉटरमार्क प्राप्त करना

अब जब आपने पीडीएफ दस्तावेज़ लोड कर लिया है, तो आप वॉटरमार्क जानकारी प्राप्त करने के लिए विशिष्ट पृष्ठ कलाकृतियों के माध्यम से पुनरावृति कर सकते हैं। ऐसे:

```csharp
// कलाकृतियाँ ब्राउज़ करें और वॉटरमार्क उपप्रकार, पाठ और स्थान प्राप्त करें
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

उपरोक्त कोड पीडीएफ दस्तावेज़ के पहले पृष्ठ पर सभी कलाकृतियों के माध्यम से घूमता है और सामने आए प्रत्येक वॉटरमार्क के उपप्रकार, पाठ और आयत (स्थान) को प्रदर्शित करता है।

### .NET के लिए Aspose.PDF का उपयोग करके वॉटरमार्क प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// पुनरावृति करें और टब-प्रकार, पाठ और आर्टिफैक्ट का स्थान प्राप्त करें
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## निष्कर्ष

बधाई हो! आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ से वॉटरमार्क जानकारी कैसे प्राप्त करें। अब आप इस ज्ञान का उपयोग अपने पीडीएफ दस्तावेजों में वॉटरमार्क का विश्लेषण और प्रसंस्करण करने के लिए कर सकते हैं।

### पीडीएफ फाइल से वॉटरमार्क प्राप्त करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में वॉटरमार्क क्या है, और मुझे इसकी जानकारी निकालने की आवश्यकता क्यों होगी?

उ: पीडीएफ दस्तावेज़ में वॉटरमार्क एक पहचानने योग्य छवि या पाठ है जो दस्तावेज़ की सामग्री पर लगाया जाता है, अक्सर इसकी स्थिति, स्वामित्व या गोपनीय प्रकृति को इंगित करने के लिए। वॉटरमार्क जानकारी निकालना दस्तावेज़ की प्रामाणिकता का विश्लेषण करने, दस्तावेज़ स्रोत की पहचान करने, या वॉटरमार्क उपस्थिति के आधार पर दस्तावेज़ों को संसाधित करने के लिए उपयोगी हो सकता है।

#### प्रश्न: प्रदान किया गया C# स्रोत कोड पीडीएफ फाइल से वॉटरमार्क जानकारी निकालने में कैसे मदद करता है?

 ए: प्रदान किया गया कोड दर्शाता है कि मौजूदा पीडीएफ दस्तावेज़ को कैसे लोड किया जाए, किसी विशिष्ट पृष्ठ की कलाकृतियों के माध्यम से पुनरावृत्त किया जाए और वॉटरमार्क के बारे में जानकारी निकाली जाए। यह इसे एक्सेस करके करता है`Subtype`, `Text` , और`Rectangle` प्रत्येक कलाकृति के गुण.

####  प्रश्न: क्या करता है`Subtype` property of an artifact represent?

 ए: द`Subtype` किसी कलाकृति की संपत्ति कलाकृति के प्रकार को दर्शाती है। वॉटरमार्क के लिए, यह इंगित करता है कि कलाकृति वॉटरमार्क है।

#### प्रश्न: कोड पृष्ठ पर वॉटरमार्क का स्थान (आयत) कैसे निर्धारित करता है?

 ए: कोड का उपयोग करता है`Rectangle` वॉटरमार्क का स्थान निर्धारित करने के लिए कलाकृति की संपत्ति।`Rectangle` प्रॉपर्टी पृष्ठ पर आर्टिफैक्ट की बाउंडिंग आयत का प्रतिनिधित्व करती है।

#### प्रश्न: क्या मैं वॉटरमार्क के बारे में अतिरिक्त जानकारी, जैसे उसका स्वरूप या रंग, निकालने के लिए कोड को संशोधित कर सकता हूँ?

उत्तर: हां, यदि ऐसी जानकारी उपलब्ध है और आपके उपयोग के मामले में प्रासंगिक है, तो आप कलाकृति के अन्य गुणों, जैसे कि उसका स्वरूप या रंग, तक पहुंचने के लिए कोड को संशोधित कर सकते हैं।

#### प्रश्न: क्या मैं इस कोड का उपयोग करके पीडीएफ दस्तावेज़ के कई पृष्ठों से वॉटरमार्क जानकारी निकाल सकता हूँ?

उ: हां, आप विभिन्न पृष्ठों से कलाकृतियों तक पहुंचने के लिए लूप में पेज इंडेक्स को बदलकर एकाधिक पृष्ठों पर कलाकृतियों के माध्यम से पुनरावृत्त करने के लिए कोड को संशोधित कर सकते हैं।

#### प्रश्न: यदि निर्दिष्ट पृष्ठ पर कोई वॉटरमार्क न हो तो क्या होगा?

उ: यदि निर्दिष्ट पृष्ठ पर कोई वॉटरमार्क नहीं है, तो लूप निष्पादित नहीं होगा, और कोई वॉटरमार्क जानकारी प्रदर्शित नहीं की जाएगी।

#### प्रश्न: मैं आगे की प्रक्रिया के लिए निकाली गई वॉटरमार्क जानकारी का उपयोग कैसे कर सकता हूं?

उ: निकाली गई वॉटरमार्क जानकारी का उपयोग विभिन्न उद्देश्यों के लिए किया जा सकता है, जैसे लॉगिंग, विश्लेषण, रिपोर्टिंग, या वॉटरमार्क की उपस्थिति या गुणों के आधार पर विशिष्ट कार्यों का स्वचालन।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में अन्य प्रकार की कलाकृतियों के बारे में जानकारी निकालने के लिए इस कोड को संशोधित कर सकता हूं?

उत्तर: हां, आप समान दृष्टिकोण का उपयोग करके अन्य प्रकार की कलाकृतियों के गुणों तक पहुंच कर उनके बारे में जानकारी निकालने के लिए कोड को संशोधित कर सकते हैं।

#### प्रश्न: मैं उन वॉटरमार्क तक कैसे पहुंच सकता हूं जो कलाकृतियां नहीं हैं लेकिन पीडीएफ सामग्री का हिस्सा हैं?

उ: वॉटरमार्क जो कलाकृतियाँ नहीं हैं, वे स्वयं पीडीएफ सामग्री का हिस्सा हो सकते हैं, जैसे चित्र या पाठ। इस प्रकार के वॉटरमार्क के बारे में जानकारी निकालने के लिए, आपको पीडीएफ सामग्री का विश्लेषण करने और वॉटरमार्क का प्रतिनिधित्व करने वाले विशिष्ट तत्वों की पहचान करने की आवश्यकता हो सकती है।