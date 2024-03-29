---
title: रेडियो की बटन
linktitle: रेडियो की बटन
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ आसानी से अपने PDF दस्तावेज़ों में रेडियो बटन जोड़ें।
type: docs
weight: 220
url: /hi/net/programming-with-forms/radio-button/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में रेडियो बटन कैसे जोड़ें। इस प्रक्रिया में आपका मार्गदर्शन करने के लिए हम चरण दर चरण C# स्रोत कोड की व्याख्या करेंगे।

## चरण 1: तैयारी

सुनिश्चित करें कि आपने आवश्यक लाइब्रेरीज़ आयात कर ली हैं और अपनी दस्तावेज़ निर्देशिका के लिए पथ निर्धारित कर लिया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ ऑब्जेक्ट को त्वरित करें

नया पीडीएफ दस्तावेज़ बनाने के लिए दस्तावेज़ ऑब्जेक्ट को इंस्टेंट करें:

```csharp
Document pdfDocument = new Document();
```

## चरण 3: एक पेज जोड़ें

पीडीएफ दस्तावेज़ में एक पेज जोड़ें:

```csharp
pdfDocument.Pages.Add();
```

## चरण 4: रेडियोबटनफ़ील्ड ऑब्जेक्ट को इंस्टेंट करें

एक तर्क के रूप में पृष्ठ संख्या निर्दिष्ट करते हुए रेडियोबटनफ़ील्ड ऑब्जेक्ट को इंस्टेंटियेट करें:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## चरण 5: रेडियो बटन विकल्प जोड़ें

रेक्टेंगल ऑब्जेक्ट के साथ प्रत्येक विकल्प के निर्देशांक निर्दिष्ट करके RadioButtonField ऑब्जेक्ट में रेडियो बटन विकल्प जोड़ें:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## चरण 6: फॉर्म में रेडियो बटन जोड़ें

दस्तावेज़ के फॉर्म ऑब्जेक्ट में रेडियो बटन जोड़ें:

```csharp
pdfDocument.Form.Add(radio);
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

बनाए गए पीडीएफ दस्तावेज़ को सहेजें:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// त्वरित दस्तावेज़ ऑब्जेक्ट
	Document pdfDocument = new Document();
	// पीडीएफ फाइल में एक पेज जोड़ें
	pdfDocument.Pages.Add();
	// तर्क के रूप में पृष्ठ संख्या के साथ RadioButtonField ऑब्जेक्ट स्थापित करें
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// पहला रेडियो बटन विकल्प जोड़ें और रेक्टेंगल ऑब्जेक्ट का उपयोग करके इसका मूल भी निर्दिष्ट करें
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// दूसरा रेडियो बटन विकल्प जोड़ें
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// दस्तावेज़ ऑब्जेक्ट का ऑब्जेक्ट बनाने के लिए रेडियो बटन जोड़ें
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// पीडीएफ फाइल को सेव करें
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में रेडियो बटन कैसे जोड़ा जाए। इन चरणों का पालन करके, आप आसानी से एक रेडियो बटन बना सकते हैं और इसे अपने पीडीएफ दस्तावेज़ में एक विशिष्ट पृष्ठ पर रख सकते हैं।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं रेडियो बटन का स्वरूप, जैसे उसका आकार और रंग, अनुकूलित कर सकता हूँ?

 उत्तर: हां, आप इसका उपयोग करके रेडियो बटन के स्वरूप को अनुकूलित कर सकते हैं`Rectangle` वस्तु के आकार और स्थिति को परिभाषित करने के लिए उसके निर्देशांक। .NET के लिए Aspose.PDF आपको अपनी आवश्यकताओं के अनुरूप रेडियो बटन के स्वरूप को समायोजित करने की अनुमति देता है।

#### प्रश्न: क्या मैं एक ही पृष्ठ पर विभिन्न समूहों के साथ अनेक रेडियो बटन जोड़ सकता हूँ?

उ: हाँ, आप एक ही पृष्ठ पर विभिन्न समूहों के साथ अनेक रेडियो बटन जोड़ सकते हैं। रेडियो बटनों के प्रत्येक समूह का एक अद्वितीय नाम हो सकता है, और एक समय में प्रत्येक समूह के भीतर केवल एक विकल्प का चयन किया जा सकता है।

#### प्रश्न: मैं रेडियो बटन विकल्पों में एक लेबल या टेक्स्ट विवरण कैसे जोड़ सकता हूँ?

 उ: रेडियो बटन विकल्पों में एक लेबल या टेक्स्ट विवरण जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`TextStamp`विशिष्ट निर्देशांक पर पीडीएफ दस्तावेज़ पर टेक्स्ट को ओवरले करने के लिए .NET के लिए Aspose.PDF से क्लास।

#### प्रश्न: क्या .NET के लिए Aspose.PDF .NET फ्रेमवर्क के सभी संस्करणों के साथ संगत है?

उत्तर: हाँ, .NET के लिए Aspose.PDF .NET कोर और .NET मानक सहित .NET फ्रेमवर्क के सभी संस्करणों के साथ संगत है।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में रेडियो बटन विकल्प के चयन को प्रोग्रामेटिक रूप से नियंत्रित कर सकता हूं?

 उत्तर: हां, आप इसका उपयोग करके रेडियो बटन विकल्प के चयन को प्रोग्रामेटिक रूप से नियंत्रित कर सकते हैं`IsSelected` की संपत्ति`RadioButtonOption` कक्षा। यह संपत्ति आपको एक विशिष्ट विकल्प को चयनित के रूप में सेट करने की अनुमति देती है।