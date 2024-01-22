---
title: पीडीएफ फाइल में चाइल्ड बुकमार्क प्राप्त करें
linktitle: पीडीएफ फाइल में चाइल्ड बुकमार्क प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ आसानी से पीडीएफ फाइल में चाइल्ड बुकमार्क प्राप्त करें।
type: docs
weight: 80
url: /hi/net/programming-with-bookmarks/get-child-bookmarks/
---
पीडीएफ फ़ाइल में चाइल्ड बुकमार्क पुनर्प्राप्त करना बुकमार्क की पदानुक्रमित संरचना की खोज के लिए उपयोगी हो सकता है। .NET के लिए Aspose.PDF के साथ, आप निम्नलिखित स्रोत कोड का पालन करके आसानी से चाइल्ड बुकमार्क प्राप्त कर सकते हैं:

## चरण 1: आवश्यक पुस्तकालय आयात करें

शुरू करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करनी होगी। यहाँ आवश्यक आयात निर्देश है:

```csharp
using Aspose.Pdf;
```

## चरण 2: दस्तावेज़ फ़ोल्डर में पथ सेट करें

 इस चरण में, आपको उस पीडीएफ फ़ाइल वाले फ़ोल्डर का पथ निर्दिष्ट करना होगा जिससे आप बुकमार्क निकालना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"`आपके दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 3: पीडीएफ दस्तावेज़ खोलें

अब हम पीडीएफ दस्तावेज़ खोलने जा रहे हैं जिसमें से हम निम्नलिखित कोड का उपयोग करके बुकमार्क निकालना चाहते हैं:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## चरण 4: बुकमार्क और चाइल्ड बुकमार्क ब्राउज़ करें

 इस चरण में, हम दस्तावेज़ में सभी बुकमार्क का उपयोग करके पुनरावृति करेंगे`foreach` कुंडली। प्रत्येक बुकमार्क के लिए, हम शीर्षक, इटैलिक शैली, बोल्ड शैली और रंग जैसी जानकारी प्रदर्शित करेंगे। यदि बुकमार्क में चाइल्ड बुकमार्क हैं, तो हम उन्हें भी प्रदर्शित करेंगे। यहाँ संबंधित कोड है:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // चाइल्ड बुकमार्क भी ब्राउज़ करें
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### .NET के लिए Aspose.PDF का उपयोग करके चाइल्ड बुकमार्क प्राप्त करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// सभी बुकमार्क के माध्यम से लूप करें
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// चाइल्ड बुकमार्क हैं तो उनमें भी लूप करें
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## निष्कर्ष

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF के साथ चाइल्ड बुकमार्क प्राप्त करने के लिए चरण-दर-चरण मार्गदर्शिका है। आप इस कोड का उपयोग बुकमार्क की पदानुक्रमित संरचना का पता लगाने और अपने पीडीएफ दस्तावेज़ों में प्रत्येक बुकमार्क और उसके चाइल्ड बुकमार्क के बारे में विस्तृत जानकारी प्राप्त करने के लिए कर सकते हैं।

उन्नत बुकमार्क हेरफेर सुविधाओं पर अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ को अवश्य देखें।

### पीडीएफ फ़ाइल में चाइल्ड बुकमार्क प्राप्त करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ फाइल में चाइल्ड बुकमार्क क्या हैं?

उ: चाइल्ड बुकमार्क वे बुकमार्क होते हैं जो पैरेंट बुकमार्क के अंतर्गत नेस्टेड होते हैं। वे एक पदानुक्रमित संरचना बनाते हैं, जो पीडीएफ दस्तावेज़ के भीतर अधिक व्यवस्थित और विस्तृत नेविगेशन अनुभव की अनुमति देता है।

#### प्रश्न: मैं पीडीएफ फाइल से चाइल्ड बुकमार्क क्यों पुनर्प्राप्त करना चाहूंगा?

उ: चाइल्ड बुकमार्क पुनर्प्राप्त करने से आपको दस्तावेज़ के विभिन्न अनुभागों के बीच संबंधों और पदानुक्रम को समझने में मदद मिलती है। यह जानकारी जटिल संरचनाओं या संगठन के कई स्तरों वाले दस्तावेज़ों के लिए विशेष रूप से उपयोगी हो सकती है।

#### प्रश्न: मैं अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी कैसे आयात करूं?

उ: अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करने के लिए, निम्नलिखित आयात निर्देश का उपयोग करें:

```csharp
using Aspose.Pdf;
```

यह निर्देश आपको .NET के लिए Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुंचने में सक्षम बनाता है।

#### प्रश्न: मैं दस्तावेज़ फ़ोल्डर का पथ कैसे निर्दिष्ट करूं?

 उत्तर: दिए गए स्रोत कोड में, बदलें`"YOUR DOCUMENT DIRECTORY"` उस पीडीएफ फ़ाइल वाले फ़ोल्डर के वास्तविक पथ के साथ जिसमें से आप चाइल्ड बुकमार्क निकालना चाहते हैं। यह सुनिश्चित करता है कि कोड लक्ष्य पीडीएफ फाइल का पता लगा सकता है।

#### प्रश्न: चाइल्ड बुकमार्क निकालने के लिए मैं पीडीएफ दस्तावेज़ कैसे खोलूं?

उ: बुकमार्क निकालने के लिए पीडीएफ दस्तावेज़ खोलने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

 प्रतिस्थापित करें`"GetChildBookmarks.pdf"` वास्तविक फ़ाइल नाम के साथ.

#### प्रश्न: मैं चाइल्ड बुकमार्क जानकारी को कैसे दोहराऊं और प्रदर्शित करूं?

 उ: का उपयोग करके दस्तावेज़ में सभी बुकमार्क को लूप करें`foreach` कुंडली। प्रत्येक बुकमार्क के लिए, शीर्षक, इटैलिक शैली, बोल्ड शैली, रंग जैसी जानकारी प्रदर्शित करें, और यदि इसमें चाइल्ड बुकमार्क हैं, तो उनके माध्यम से भी पुनरावृत्त करें:

```csharp
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
    Console.WriteLine("Title: " + outlineItem.Title);
    Console.WriteLine("Italic: " + outlineItem.Italic);
    Console.WriteLine("Bold: " + outlineItem.Bold);
    Console.WriteLine("Color: " + outlineItem.Color);
    
    if (outlineItem.Count > 0)
    {
        Console.WriteLine("Child bookmarks");
        
        // चाइल्ड बुकमार्क भी ब्राउज़ करें
        foreach (OutlineItemCollection childOutline in outlineItem)
        {
            Console.WriteLine(childOutline.Title);
            Console.WriteLine(childOutline.Italic);
            Console.WriteLine(childOutline.Bold);
            Console.WriteLine(childOutline.Color);
        }
    }
}
```

#### प्रश्न: क्या मैं समान दृष्टिकोण का उपयोग करके चाइल्ड बुकमार्क के अन्य गुण निकाल सकता हूँ?

 उत्तर: हां, आप इसका उपयोग करके चाइल्ड बुकमार्क के विभिन्न गुण निकाल सकते हैं`OutlineItemCollection` वस्तु। उपलब्ध संपत्तियों की विस्तृत सूची के लिए Aspose.PDF दस्तावेज़ देखें।

#### प्रश्न: क्या मेरे द्वारा पुनर्प्राप्त किए जा सकने वाले चाइल्ड बुकमार्क की संख्या की कोई सीमा है?

उ: आमतौर पर इस पद्धति का उपयोग करके आप कितने चाइल्ड बुकमार्क प्राप्त कर सकते हैं, इसकी कोई सख्त सीमा नहीं है। हालाँकि, अत्यधिक संख्या में चाइल्ड बुकमार्क वाले बहुत बड़े दस्तावेज़ों के लिए कुशल मेमोरी प्रबंधन की आवश्यकता हो सकती है।

#### प्रश्न: यदि चाइल्ड बुकमार्क में अतिरिक्त नेस्टेड चाइल्ड बुकमार्क हों तो क्या होगा?

उ: प्रदान किया गया कोड चाइल्ड बुकमार्क के सभी स्तरों के माध्यम से पुनरावर्ती रूप से पुनरावृत्त होगा, जिससे आप नेस्टेड चाइल्ड बुकमार्क से भी जानकारी प्राप्त कर सकेंगे।

#### प्रश्न: मैं निकाली गई चाइल्ड बुकमार्क जानकारी का उपयोग कैसे कर सकता हूं?

उ: आप निकाली गई चाइल्ड बुकमार्क जानकारी का उपयोग विश्लेषण, दस्तावेज़ीकरण, या अपने अनुप्रयोगों के भीतर कस्टम नेविगेशन इंटरफेस बनाने के लिए कर सकते हैं।