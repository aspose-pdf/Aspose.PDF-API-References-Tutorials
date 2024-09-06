---
title: टेक्स्ट प्रतिस्थापन का उपयोग करके सामग्री को पुनर्व्यवस्थित करें
linktitle: टेक्स्ट प्रतिस्थापन का उपयोग करके सामग्री को पुनर्व्यवस्थित करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ पाठ प्रतिस्थापन का उपयोग करके PDF दस्तावेज़ में सामग्री को पुनर्व्यवस्थित करना सीखें।
type: docs
weight: 270
url: /hi/net/programming-with-text/rearrange-contents-using-text-replacement/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी के साथ टेक्स्ट रिप्लेसमेंट का उपयोग करके PDF दस्तावेज़ में सामग्री को कैसे पुनर्व्यवस्थित किया जाए। हम PDF लोड करने, विशिष्ट टेक्स्ट अंशों की खोज करने, टेक्स्ट को बदलने और दिए गए C# स्रोत कोड का उपयोग करके संशोधित PDF को सहेजने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आपकी पीडीएफ फाइलें स्थित हैं।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपनी पीडीएफ फाइलों के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत पीडीएफ लोड करें

 इसके बाद, हम स्रोत पीडीएफ दस्तावेज़ को लोड करते हैं`Document` Aspose.PDF लाइब्रेरी से क्लास.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## चरण 3: टेक्स्ट अंशों को खोजें और बदलें

 हम एक बनाते हैं`TextFragmentAbsorber` ऑब्जेक्ट को रेगुलर एक्सप्रेशन के साथ विशिष्ट टेक्स्ट अंशों की खोज करने के लिए उपयोग किया जाता है। फिर, हम टेक्स्ट अंशों के माध्यम से पुनरावृति करते हैं, उनके फ़ॉन्ट, आकार, रंग को अनुकूलित करते हैं, और टेक्स्ट को प्रतिस्थापित करते हैं।

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## चरण 4: संशोधित पीडीएफ को सहेजें

अंत में, हम संशोधित पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट प्रतिस्थापन का उपयोग करके सामग्री को पुनर्व्यवस्थित करने के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// स्रोत पीडीएफ फ़ाइल लोड करें
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// नियमित अभिव्यक्ति के साथ TextFragment अवशोषक ऑब्जेक्ट बनाएँ
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// प्रत्येक TextFragment को प्रतिस्थापित करें
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// प्रतिस्थापित किये जा रहे पाठ खंड का फ़ॉन्ट सेट करें
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// फ़ॉन्ट आकार सेट करें
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// टेक्स्ट को प्लेसहोल्डर से बड़ी स्ट्रिंग से बदलें
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// परिणामी PDF सहेजें
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने .NET के लिए Aspose.PDF लाइब्रेरी के साथ टेक्स्ट प्रतिस्थापन का उपयोग करके PDF दस्तावेज़ में सामग्री को पुनर्व्यवस्थित करना सीखा है। चरण-दर-चरण मार्गदर्शिका का पालन करके और प्रदान किए गए C# कोड को निष्पादित करके, आप विशिष्ट टेक्स्ट अंशों की खोज कर सकते हैं, उनकी उपस्थिति को अनुकूलित कर सकते हैं, और PDF दस्तावेज़ में टेक्स्ट को बदल सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट प्रतिस्थापन का उपयोग करके सामग्री को पुनर्व्यवस्थित करें" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "टेक्स्ट रिप्लेसमेंट का उपयोग करके सामग्री को पुनर्व्यवस्थित करें" ट्यूटोरियल दर्शाता है कि टेक्स्ट रिप्लेसमेंट करके PDF दस्तावेज़ में सामग्री को पुनर्व्यवस्थित करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल आपको PDF लोड करने, विशिष्ट टेक्स्ट अंशों की खोज करने, टेक्स्ट को बदलने और संशोधित PDF को सहेजने में मदद करने के लिए चरण-दर-चरण मार्गदर्शिका और C# स्रोत कोड प्रदान करता है।

#### प्रश्न: मैं PDF दस्तावेज़ में सामग्री को पुनः व्यवस्थित क्यों करना चाहूंगा?

उत्तर: PDF दस्तावेज़ में सामग्री को पुनर्व्यवस्थित करना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे कि टेक्स्ट को अपडेट करना, लेआउट को फिर से फ़ॉर्मेट करना या सुधार करना। यह तकनीक आपको PDF की संरचना और उपस्थिति को संरक्षित करते हुए उसकी सामग्री को गतिशील रूप से संशोधित करने की अनुमति देती है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे स्थापित करूँ?

उत्तर: दस्तावेज़ निर्देशिका सेट अप करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` चर को उस निर्देशिका के पथ के साथ जोड़ें जहां आपकी पीडीएफ फाइलें स्थित हैं।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में पाठ प्रतिस्थापन कैसे करूँ?

 उत्तर: यह ट्यूटोरियल आपको पीडीएफ में विशिष्ट पाठ अंशों की खोज करने की प्रक्रिया के माध्यम से मार्गदर्शन करता है।`TextFragmentAbsorber`यह दर्शाता है कि पाठ अंशों की उपस्थिति को कैसे अनुकूलित किया जाए और उनकी सामग्री को कैसे बदला जाए।

#### प्रश्न: क्या मैं प्रतिस्थापित पाठ का फ़ॉन्ट, आकार और रंग अनुकूलित कर सकता हूँ?

 उत्तर: हां, आप प्रतिस्थापित पाठ के फ़ॉन्ट, आकार और रंग को संशोधित करके अनुकूलित कर सकते हैं।`TextState` के गुण`TextFragment` यह ट्यूटोरियल पाठ का फ़ॉन्ट, फ़ॉन्ट आकार और अग्रभूमि रंग सेट करने का एक उदाहरण प्रदान करता है।

#### प्रश्न: मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: पाठ प्रतिस्थापन करने और पाठ अंशों को अनुकूलित करने के बाद, आप संशोधित पीडीएफ दस्तावेज़ को निम्न का उपयोग करके सहेज सकते हैं:`Save` की विधि`Document` वर्ग। वांछित आउटपुट फ़ाइल पथ को तर्क के रूप में प्रदान करें`Save` तरीका।

#### प्रश्न: इस ट्यूटोरियल का अपेक्षित आउटपुट क्या है?

उत्तर: ट्यूटोरियल का अनुसरण करके और दिए गए C# कोड को निष्पादित करके, आप एक संशोधित PDF दस्तावेज़ तैयार करेंगे, जिसमें विशिष्ट पाठ अंशों को प्रतिस्थापित किया गया है और आपकी विशिष्टताओं के अनुसार अनुकूलित किया गया है।

#### प्रश्न: क्या मैं पाठ खोज के लिए विभिन्न नियमित अभिव्यक्तियों का उपयोग कर सकता हूँ?

 उत्तर: हां, आप पीडीएफ दस्तावेज़ में विशिष्ट टेक्स्ट अंशों की खोज करने के लिए विभिन्न नियमित अभिव्यक्तियों का उपयोग कर सकते हैं। ट्यूटोरियल में दिया गया उदाहरण दर्शाता है कि कैसे एक नियमित अभिव्यक्ति बनाई जाती है।`TextFragmentAbsorber`पाठ खोजने और बदलने के लिए एक विशिष्ट नियमित अभिव्यक्ति के साथ ऑब्जेक्ट।

#### प्रश्न: क्या इस ट्यूटोरियल के लिए वैध एस्पोज लाइसेंस आवश्यक है?

उत्तर: हां, इस ट्यूटोरियल को सही तरीके से काम करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से एक पूर्ण लाइसेंस खरीद सकते हैं या 30-दिन का अस्थायी लाइसेंस प्राप्त कर सकते हैं।