---
title: सभी पेजों को पीएनजी में कनवर्ट करें
linktitle: सभी पेजों को पीएनजी में कनवर्ट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ PDF दस्तावेज़ के सभी पृष्ठों को आसानी से PNG फ़ाइलों में परिवर्तित करें।
type: docs
weight: 60
url: /hi/net/programming-with-images/convert-all-pages-to-png/
---
यह मार्गदर्शिका आपको चरण दर चरण बताएगी कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के सभी पृष्ठों को PNG फ़ाइलों में कैसे परिवर्तित किया जाए। सुनिश्चित करें कि आपने अपना परिवेश पहले ही सेट कर लिया है और नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें

 शुरू करने से पहले, सुनिश्चित करें कि आपने दस्तावेज़ों के लिए सही निर्देशिका सेट की है। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` कोड में उस निर्देशिका के पथ के साथ जहां आपका पीडीएफ दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ खोलें

इस चरण में, हम इसका उपयोग करके पीडीएफ दस्तावेज़ खोलेंगे`Document` Aspose.PDF की कक्षा। उपयोग`Document` कंस्ट्रक्टर और पीडीएफ दस्तावेज़ के लिए पथ पास करें।

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## चरण 3: प्रत्येक पृष्ठ को पीएनजी में बदलें

 इस चरण में, हम पीडीएफ दस्तावेज़ के प्रत्येक पृष्ठ पर जाएंगे और उन्हें अलग-अलग पीएनजी फाइलों में परिवर्तित करेंगे। हम एक का उपयोग करेंगे`for` सभी पृष्ठों के माध्यम से पुनरावृत्त करने के लिए लूप।

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // पीएनजी छवि को सहेजने के लिए एक स्ट्रीम बनाएं
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // निर्दिष्ट विशेषताओं के साथ एक पीएनजी डिवाइस बनाएं
         // चौड़ाई, ऊंचाई, रिज़ॉल्यूशन, गुणवत्ता
         // गुणवत्ता [0-100], 100 अधिकतम है
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // किसी विशिष्ट पृष्ठ को कनवर्ट करें और छवि को स्ट्रीम में सहेजें
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // स्ट्रीम बंद करें
         imageStream.Close();
     }
}
```

### .NET के लिए Aspose.PDF का उपयोग करके सभी पेजों को PNG में कनवर्ट करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// निर्दिष्ट विशेषताओं के साथ पीएनजी डिवाइस बनाएं
		// चौड़ाई, ऊंचाई, रिज़ॉल्यूशन, गुणवत्ता
		// गुणवत्ता [0-100], 100 अधिकतम है
		// रिज़ॉल्यूशन ऑब्जेक्ट बनाएं
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		//किसी विशेष पृष्ठ को रूपांतरित करें और छवि को स्ट्रीम करने के लिए सहेजें
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// स्ट्रीम बंद करें
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के सभी पृष्ठों को सफलतापूर्वक PNG फ़ाइलों में परिवर्तित कर लिया है। अलग-अलग पीएनजी फ़ाइलें निर्दिष्ट निर्देशिका में सहेजी जाती हैं। अब आप इन पीएनजी फाइलों का उपयोग अपने प्रोजेक्ट या एप्लिकेशन में कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीएनजी क्या है, और मुझे पीडीएफ पेजों को पीएनजी फाइलों में बदलने की आवश्यकता क्यों होगी?

उत्तर: पीएनजी (पोर्टेबल नेटवर्क ग्राफिक्स) एक व्यापक रूप से उपयोग किया जाने वाला छवि प्रारूप है जो अपने दोषरहित संपीड़न और पारदर्शी पृष्ठभूमि के लिए समर्थन के लिए जाना जाता है। पीडीएफ पृष्ठों को पीएनजी प्रारूप में परिवर्तित करना छवि गुणवत्ता को संरक्षित करने और छवि हेरफेर की सुविधा के लिए उपयोगी हो सकता है।

#### प्रश्न: .NET के लिए Aspose.PDF, PDF पृष्ठों को PNG फ़ाइलों में बदलने में कैसे सहायता करता है?

उ: .NET के लिए Aspose.PDF एक PDF दस्तावेज़ के प्रत्येक पृष्ठ को अलग-अलग PNG फ़ाइलों में परिवर्तित करने के लिए एक सुव्यवस्थित प्रक्रिया प्रदान करता है, जिससे रूपांतरण प्रक्रिया कुशल और उपयोगकर्ता के अनुकूल हो जाती है।

#### प्रश्न: पीडीएफ से पीएनजी रूपांतरण प्रक्रिया में दस्तावेज़ निर्देशिका को परिभाषित करना महत्वपूर्ण क्यों है?

उ: दस्तावेज़ निर्देशिका को परिभाषित करने से यह सुनिश्चित होता है कि पीडीएफ दस्तावेज़ सही ढंग से स्थित है, और परिणामी पीएनजी फ़ाइलें वांछित आउटपुट पथ में सहेजी जाती हैं।

#### प्रश्न: मैं पीडीएफ से पीएनजी रूपांतरण प्रक्रिया में .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ कैसे खोलूं?

 ए: का प्रयोग करें`Document` पीडीएफ दस्तावेज़ खोलने के लिए क्लास का उपयोग करें, जो रूपांतरण प्रक्रिया के लिए इनपुट के रूप में कार्य करता है।

#### प्रश्न: प्रत्येक पीडीएफ पेज का अलग-अलग पीएनजी फाइलों में रूपांतरण कैसे काम करता है?

 ए: ए`for` लूप पीडीएफ दस्तावेज़ के प्रत्येक पृष्ठ के माध्यम से पुनरावृत्त होता है। प्रत्येक पृष्ठ के लिए, एक पीएनजी छवि का उपयोग करके तैयार किया जाता है`PngDevice`, और परिणामी छवि निर्दिष्ट आउटपुट निर्देशिका में सहेजी जाती है।

#### प्रश्न: क्या मैं रूपांतरण प्रक्रिया के दौरान पीएनजी फ़ाइलों की विशेषताओं को अनुकूलित कर सकता हूँ?

उत्तर: हां, आप अपनी विशिष्ट आवश्यकताओं के अनुरूप पीएनजी फ़ाइलों की चौड़ाई, ऊंचाई, रिज़ॉल्यूशन और छवि गुणवत्ता जैसी विशेषताओं को अनुकूलित कर सकते हैं।

#### प्रश्न: क्या एकाधिक पीडीएफ दस्तावेजों को पीएनजी फाइलों में परिवर्तित करने के लिए बैच प्रोसेसिंग समर्थित है?

उ: जबकि प्रदान किया गया कोड स्निपेट व्यक्तिगत पीडीएफ दस्तावेजों के लिए डिज़ाइन किया गया है, आप कई पीडीएफ फाइलों को संभालने के लिए बैच प्रोसेसिंग लागू कर सकते हैं।

#### प्रश्न: मैं अपनी परियोजनाओं या अनुप्रयोगों में जेनरेट की गई पीएनजी फ़ाइलों का उपयोग कैसे कर सकता हूं?

उ: इस प्रक्रिया के माध्यम से उत्पन्न पीएनजी फाइलों को आपकी परियोजनाओं या अनुप्रयोगों में निर्बाध रूप से एकीकृत किया जा सकता है, जो विभिन्न उद्देश्यों के लिए बहुमुखी छवि संपत्ति प्रदान करता है।

#### प्रश्न: अन्य छवि प्रारूपों की तुलना में पीएनजी प्रारूप क्या लाभ प्रदान करता है?

उत्तर: पीएनजी प्रारूप दोषरहित संपीड़न, पारदर्शिता और उच्च छवि गुणवत्ता का समर्थन करता है, जो इसे तेज किनारों, पाठ और समान रंग के क्षेत्रों वाली छवियों के लिए उपयुक्त बनाता है।