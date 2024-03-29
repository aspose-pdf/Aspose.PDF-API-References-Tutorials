---
title: क्षैतिज और लंबवत रेडियो बटन
linktitle: क्षैतिज और लंबवत रेडियो बटन
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ अपने PDF दस्तावेज़ों में आसानी से क्षैतिज और ऊर्ध्वाधर रेडियो बटन बनाएं।
type: docs
weight: 180
url: /hi/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में क्षैतिज और लंबवत रूप से व्यवस्थित रेडियो बटन कैसे बनाएं। इस प्रक्रिया में आपका मार्गदर्शन करने के लिए हम चरण दर चरण C# स्रोत कोड की व्याख्या करेंगे।

## चरण 1: तैयारी

सुनिश्चित करें कि आपने आवश्यक लाइब्रेरीज़ आयात कर ली हैं और अपनी दस्तावेज़ निर्देशिका के लिए पथ निर्धारित कर लिया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें

मौजूदा पीडीएफ दस्तावेज़ लोड करें:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## चरण 3: रेडियो बटन विकल्पों को अनुकूलित करें

निम्नलिखित गुण सेट करके रेडियो बटन विकल्पों को अनुकूलित करें:

```csharp
formEditor. RadioGap = 4; // दो रेडियो बटन विकल्पों के बीच की दूरी
formEditor. RadioHoriz = true; //रेडियो बटनों का क्षैतिज लेआउट
formEditor.RadioButtonItemSize = 20; // रेडियो बटन का आकार
formEditor.Facade.BorderWidth = 1; // रेडियो बटन बॉर्डर की चौड़ाई
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // रेडियो बटन बॉर्डर का रंग
```

## चरण 4: क्षैतिज रेडियो बटन जोड़ें

फ़ील्ड के विकल्प और स्थिति निर्दिष्ट करके क्षैतिज रूप से व्यवस्थित रेडियो बटन जोड़ें:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## चरण 5: लंबवत रेडियो बटन जोड़ें

फ़ील्ड के विकल्प और स्थिति निर्दिष्ट करके लंबवत रूप से व्यवस्थित रेडियो बटन जोड़ें:

```csharp
formEditor. RadioHoriz = false; // रेडियो बटनों का लंबवत लेआउट
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## चरण 6: दस्तावेज़ सहेजें

संशोधित पीडीएफ दस्तावेज़ सहेजें:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके क्षैतिज और लंबवत रेडियो बटन के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// पहले से सहेजे गए दस्तावेज़ को लोड करें
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// रेडियोगैप दो रेडियो बटन विकल्पों के बीच की दूरी है।
	formEditor.RadioGap = 4;
	// क्षैतिज रेडियो बटन जोड़ें
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize यदि रेडियो बटन आइटम का आकार।
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// लंबवत स्थित अन्य रेडियो बटन जोड़ें
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// पीडीएफ दस्तावेज़ सहेजें
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में क्षैतिज और लंबवत रूप से व्यवस्थित रेडियो बटन कैसे बनाएं। इन चरणों का पालन करके, आप आसानी से रेडियो बटन के लेआउट को अनुकूलित कर सकते हैं और Aspose.PDF का उपयोग करके उन्हें अपने पीडीएफ दस्तावेज़ों में जोड़ सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में क्षैतिज और लंबवत रूप से व्यवस्थित रेडियो बटन क्या हैं?

उ: पीडीएफ दस्तावेज़ में क्षैतिज और लंबवत रूप से व्यवस्थित रेडियो बटन रेडियो बटन विकल्पों के लेआउट ओरिएंटेशन को संदर्भित करते हैं। क्षैतिज लेआउट रेडियो बटन विकल्पों को एक साथ रखता है, जिससे उपयोगकर्ता बाएं से दाएं चयन कर सकते हैं। दूसरी ओर, लंबवत लेआउट, रेडियो बटन विकल्पों को एक-दूसरे के ऊपर रखता है, जिससे उपयोगकर्ता ऊपर से नीचे तक चयन करने में सक्षम होते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.PDF में रेडियो बटन विकल्पों की उपस्थिति को कैसे अनुकूलित करूं?

उ: आप कई गुणों को समायोजित करके .NET के लिए Aspose.PDF में रेडियो बटन विकल्पों की उपस्थिति को अनुकूलित कर सकते हैं। एपीआई दो रेडियो बटन विकल्पों के बीच की दूरी निर्धारित करने के लिए विकल्प प्रदान करता है (`RadioGap`), लेआउट ओरिएंटेशन (`RadioHoriz`), रेडियो बटन आइटम का आकार (`RadioButtonItemSize`), बॉर्डर की चौड़ाई और रेडियो बटन का रंग, और भी बहुत कुछ।

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ में क्षैतिज और ऊर्ध्वाधर दोनों रेडियो बटन जोड़ सकता हूँ?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके एक ही पीडीएफ दस्तावेज़ में क्षैतिज और ऊर्ध्वाधर दोनों रेडियो बटन जोड़ सकते हैं। ट्यूटोरियल में प्रदान किया गया नमूना स्रोत कोड दर्शाता है कि पहले क्षैतिज रूप से व्यवस्थित रेडियो बटन कैसे जोड़ें और फिर उसी पीडीएफ दस्तावेज़ में लंबवत रूप से व्यवस्थित रेडियो बटन का एक और सेट कैसे जोड़ें।

#### प्रश्न: क्या मैं रेडियो बटनों के प्रत्येक समूह के लिए अलग-अलग रेडियो बटन विकल्प सेट कर सकता हूँ?

 उत्तर: हाँ, आप रेडियो बटनों के प्रत्येक समूह के लिए अलग-अलग रेडियो बटन विकल्प सेट कर सकते हैं। प्रत्येक समूह में एक अद्वितीय होना चाहिए`RadioButtonField` वस्तु, और`RadioButtonOptionField` प्रत्येक समूह के भीतर वस्तुओं को एक ही पृष्ठ और उनके विकल्पों के लिए अद्वितीय नाम साझा करने चाहिए। यह सुनिश्चित करता है कि प्रत्येक समूह के रेडियो बटन सही ढंग से काम करते हैं, और चयन परस्पर अनन्य हैं।

#### प्रश्न: क्या रेडियो बटन की लेआउट और उपस्थिति सेटिंग्स सभी पीडीएफ दर्शकों और अनुप्रयोगों में समर्थित हैं?

उ: हां, रेडियो बटन की लेआउट और उपस्थिति सेटिंग्स सभी मानक-अनुपालक पीडीएफ दर्शकों और अनुप्रयोगों में समर्थित हैं। पीडीएफ विनिर्देश रेडियो बटन और उनकी विभिन्न विशेषताओं को परिभाषित करता है, जिससे उन्हें पीडीएफ प्रारूप में सार्वभौमिक रूप से मान्यता प्राप्त होती है। हालाँकि, विभिन्न प्लेटफार्मों पर लगातार रेंडरिंग सुनिश्चित करने के लिए विभिन्न पीडीएफ दर्शकों में रेडियो बटन की उपस्थिति और व्यवहार का परीक्षण करना आवश्यक है।