---
title: पीडीएफ से पीएनजी फ़ॉन्ट संकेत
linktitle: पीडीएफ से पीएनजी फ़ॉन्ट संकेत
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके फ़ॉन्ट संकेत के साथ पीडीएफ को पीएनजी में परिवर्तित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 160
url: /hi/net/document-conversion/pdf-to-png-font-hinting/
---
इस ट्यूटोरियल में, हम आपको फॉन्ट हिंटिंग को सक्षम करते हुए .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ को पीएनजी छवियों में परिवर्तित करने की प्रक्रिया के बारे में बताएंगे। फ़ॉन्ट संकेत एक ऐसी तकनीक है जो छोटे फ़ॉन्ट की पठनीयता में सुधार करती है। नीचे दिए गए चरणों का पालन करके, आप पीडीएफ के प्रत्येक पृष्ठ को फ़ॉन्ट संकेत के साथ पीएनजी छवि में परिवर्तित करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आप निम्नलिखित शर्तें पूरी करते हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है।
- विजुअल स्टूडियो जैसा विकास वातावरण।

## चरण 1: स्रोत पीडीएफ दस्तावेज़ खोलना
इस चरण में, हम .NET के लिए Aspose.PDF का उपयोग करके स्रोत PDF फ़ाइल खोलेंगे। नीचे दिए गए कोड का पालन करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` उस वास्तविक निर्देशिका के साथ जहां आपकी पीडीएफ फाइल स्थित है।

## चरण 2: फ़ॉन्ट संकेत सक्षम करें
पीडीएफ फाइल खोलने के बाद, हम रेंडरिंग विकल्पों का उपयोग करके फ़ॉन्ट संकेत सक्षम करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// फ़ॉन्ट संकेत सक्षम करने के लिए रेंडरिंग विकल्प बनाएं
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## चरण 3: पीएनजी छवियों में कनवर्ट करें
अब हम पीडीएफ के प्रत्येक पृष्ठ को फ़ॉन्ट संकेत के साथ पीएनजी छवि में परिवर्तित करने जा रहे हैं। निम्नलिखित कोड का प्रयोग करें:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // निर्दिष्ट विशेषताओं के साथ एक PNGDevice ऑब्जेक्ट बनाएं
         // चौड़ाई, ऊंचाई, रिज़ॉल्यूशन, गुणवत्ता
         // गुणवत्ता [0-100], 100 अधिकतम है
         // एक रिज़ॉल्यूशन ऑब्जेक्ट बनाएं
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // पूर्वनिर्धारित रेंडरिंग विकल्प सेट करें
         pngDevice.RenderingOptions = opts;

         // किसी विशिष्ट पृष्ठ को कनवर्ट करें और छवि को स्ट्रीम में सहेजें
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // स्ट्रीम बंद करें
         imageStream.Close();
     }
}
```

उपरोक्त कोड पीडीएफ के प्रत्येक पृष्ठ को फ़ॉन्ट संकेत के साथ पीएनजी छवि में परिवर्तित करता है और प्रत्येक छवि को एक अलग पीएनजी फ़ाइल के रूप में सहेजता है।

### .NET के लिए Aspose.PDF का उपयोग करके PDF से PNGFont संकेत के लिए उदाहरण स्रोत कोड

```csharp
try
{
	
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// दस्तावेज़ खोलें
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// फ़ॉन्ट संकेत सक्षम करने के लिए Aspose.Pdf.RenderingOptions बनाएं
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
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
			// पूर्वनिर्धारित रेंडरिंग विकल्प सेट करें
			pngDevice.RenderingOptions = opts;

			//किसी विशेष पृष्ठ को रूपांतरित करें और छवि को स्ट्रीम करने के लिए सहेजें
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// स्ट्रीम बंद करें
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.PDF का उपयोग करके फ़ॉन्ट संकेत के साथ पीडीएफ को पीएनजी छवियों में परिवर्तित करने की चरण-दर-चरण प्रक्रिया को कवर किया। ऊपर उल्लिखित निर्देशों का पालन करके, अब आप पीडीएफ के प्रत्येक पृष्ठ को फ़ॉन्ट संकेत के साथ पीएनजी छवि में बदलने में सक्षम होना चाहिए। यह सुविधा तब उपयोगी होती है जब आप पीएनजी छवियों में कनवर्ट करते समय छोटे फ़ॉन्ट की पठनीयता बनाए रखना चाहते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: फ़ॉन्ट संकेत क्या है, और पीडीएफ को पीएनजी में परिवर्तित करते समय यह महत्वपूर्ण क्यों है?

उत्तर: फ़ॉन्ट संकेत एक ऐसी तकनीक है जिसका उपयोग छोटे फ़ॉन्ट के आकार और स्थिति को समायोजित करके उनकी पठनीयता में सुधार करने के लिए किया जाता है। पीडीएफ को पीएनजी छवियों में परिवर्तित करते समय, फ़ॉन्ट संकेत सक्षम करने से यह सुनिश्चित होता है कि परिणामी पीएनजी छवियों में पाठ सुपाठ्य और स्पष्ट रहता है, खासकर छोटे फ़ॉन्ट आकारों के लिए। पीडीएफ दस्तावेजों को छवियों में परिवर्तित करते समय पाठ की गुणवत्ता और पठनीयता बनाए रखने के लिए यह महत्वपूर्ण है।

#### प्रश्न: फ़ॉन्ट संकेत पीएनजी रूपांतरण प्रक्रिया को कैसे प्रभावित करता है?

उ: फ़ॉन्ट संकेत पीडीएफ से पीएनजी रूपांतरण प्रक्रिया के दौरान परिणामी पीएनजी छवियों में पाठ को प्रस्तुत करने के तरीके को प्रभावित करता है। फ़ॉन्ट संकेत को सक्षम करके, Aspose.PDF लाइब्रेरी यह सुनिश्चित करने के लिए फ़ॉन्ट रेंडरिंग को समायोजित करती है कि छोटे फ़ॉन्ट अपनी स्पष्टता और पठनीयता बनाए रखते हैं, जिससे पीएनजी छवियां अधिक आकर्षक और सुपाठ्य बन जाती हैं।

#### प्रश्न: क्या मैं पीएनजी रूपांतरण को अनुकूलित करने के लिए फ़ॉन्ट संकेत सेटिंग्स समायोजित कर सकता हूं?

 उ: हां, .NET लाइब्रेरी के लिए Aspose.PDF फ़ॉन्ट संकेत सेटिंग्स सहित पीएनजी रूपांतरण प्रक्रिया को अनुकूलित करने के विकल्प प्रदान करता है। दिए गए कोड उदाहरण में,`UseFontHinting` की संपत्ति`RenderingOptions` ऑब्जेक्ट पर सेट है`true` फ़ॉन्ट संकेत सक्षम करने के लिए. आप अन्य गुणों को समायोजित करके रूपांतरण प्रक्रिया को और बेहतर बना सकते हैं`RenderingOptions` अपनी आवश्यकताओं के अनुसार कक्षा।

#### प्रश्न: पीएनजी रूपांतरण प्रक्रिया में पीएनजी छवियां कैसे सहेजी जाती हैं?

उ: दिए गए कोड उदाहरण में, पीडीएफ दस्तावेज़ का प्रत्येक पृष्ठ एक अलग पीएनजी छवि में परिवर्तित हो जाता है। पीएनजी छवियों को "छवि" पैटर्न के अनुसार फ़ाइल नामों के साथ अलग-अलग फ़ाइलों के रूप में सहेजा जाता है{pageCount}_ out.png", कहाँ`{pageCount}` परिवर्तित किये जा रहे पृष्ठ की संख्या है। प्रत्येक पीएनजी छवि मूल पीडीएफ दस्तावेज़ के एक पृष्ठ का प्रतिनिधित्व करती है।