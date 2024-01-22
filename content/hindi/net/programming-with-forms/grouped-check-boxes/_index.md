---
title: पीडीएफ दस्तावेज़ में समूहीकृत चेक बॉक्स
linktitle: पीडीएफ दस्तावेज़ में समूहीकृत चेक बॉक्स
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ PDF दस्तावेज़ में आसानी से समूहीकृत चेकबॉक्स बनाएं।
type: docs
weight: 170
url: /hi/net/programming-with-forms/grouped-check-boxes/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में समूहीकृत चेकबॉक्स कैसे बनाएं। इस प्रक्रिया में आपका मार्गदर्शन करने के लिए हम चरण दर चरण C# स्रोत कोड की व्याख्या करेंगे।

## चरण 1: तैयारी

सुनिश्चित करें कि आपने आवश्यक लाइब्रेरीज़ आयात कर ली हैं और अपनी दस्तावेज़ निर्देशिका के लिए पथ निर्धारित कर लिया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ ऑब्जेक्ट को त्वरित करें

किसी दस्तावेज़ ऑब्जेक्ट को त्वरित करें:

```csharp
Document pdfDocument = new Document();
```

## चरण 3: पीडीएफ दस्तावेज़ में पेज जोड़ें

पीडीएफ दस्तावेज़ में एक पेज जोड़ें:

```csharp
Page page = pdfDocument.Pages.Add();
```

## चरण 4: रेडियोबटनफ़ील्ड ऑब्जेक्ट को इंस्टेंट करें

तर्क के रूप में पृष्ठ संख्या के साथ रेडियोबटनफ़ील्ड ऑब्जेक्ट को इंस्टेंट करें:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## चरण 5: रेडियो बटन विकल्प जोड़ें

RadioButtonOptionField ऑब्जेक्ट का उपयोग करके रेडियो बटन विकल्प जोड़ें और रेक्टेंगल ऑब्जेक्ट का उपयोग करके उनकी स्थिति निर्दिष्ट करें:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## चरण 6: रेडियो बटन विकल्पों को अनुकूलित करें

रेडियो बटन विकल्पों को उनकी शैली, सीमा और स्वरूप सेट करके अनुकूलित करें:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## चरण 7: फॉर्म में रेडियो बटन जोड़ें

दस्तावेज़ प्रपत्र ऑब्जेक्ट में रेडियो बटन जोड़ें:

```csharp
pdfDocument.Form.Add(radio);
```

## चरण 8: दस्तावेज़ सहेजें

पीडीएफ दस्तावेज़ सहेजें:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके समूहीकृत चेक बॉक्स के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// त्वरित दस्तावेज़ ऑब्जेक्ट
	Document pdfDocument = new Document();
	// पीडीएफ फाइल में एक पेज जोड़ें
	Page page = pdfDocument.Pages.Add();
	// तर्क के रूप में पृष्ठ संख्या के साथ RadioButtonField ऑब्जेक्ट स्थापित करें
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// पहला रेडियो बटन विकल्प जोड़ें और रेक्टेंगल ऑब्जेक्ट का उपयोग करके इसका मूल भी निर्दिष्ट करें
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// दस्तावेज़ ऑब्जेक्ट का ऑब्जेक्ट बनाने के लिए रेडियो बटन जोड़ें
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// पीडीएफ दस्तावेज़ सहेजें
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में समूहीकृत चेकबॉक्स कैसे बनाएं। इन चरणों का पालन करके, आप आसानी से कस्टम रेडियो बटन विकल्प जोड़ सकते हैं और Aspose.PDF का उपयोग करके उन्हें अपने पीडीएफ दस्तावेजों में बंडल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में समूहीकृत चेकबॉक्स क्या हैं?

उ: पीडीएफ दस्तावेज़ में समूहीकृत चेकबॉक्स रेडियो बटन विकल्पों के एक सेट को संदर्भित करते हैं जिन्हें एक साथ समूहीकृत किया जाता है। रेडियो बटन उपयोगकर्ताओं को परस्पर अनन्य विकल्पों के समूह से केवल एक विकल्प चुनने की अनुमति देते हैं। जब एक रेडियो बटन का चयन किया जाता है, तो उसी समूह के अन्य बटन स्वचालित रूप से अचयनित हो जाते हैं। यह समूहीकरण व्यवहार तब उपयोगी होता है जब आप उपयोगकर्ताओं को कई विकल्पों के साथ प्रस्तुत करना चाहते हैं लेकिन उनके चयन को केवल एक विकल्प तक सीमित रखना चाहते हैं।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF में समूहीकृत चेकबॉक्स की उपस्थिति को अनुकूलित कर सकता हूँ?

उ: हां, आप .NET के लिए Aspose.PDF में समूहीकृत चेकबॉक्स की उपस्थिति को अनुकूलित कर सकते हैं। एपीआई रेडियो बटन विकल्पों की शैली, सीमा और उपस्थिति निर्धारित करने के लिए विभिन्न विकल्प प्रदान करता है। आप प्रत्येक विकल्प की स्थिति को परिभाषित कर सकते हैं, विभिन्न बॉक्स शैलियों (उदाहरण के लिए, वर्ग, सर्कल, क्रॉस) के बीच चयन कर सकते हैं, और वांछित दृश्य प्रतिनिधित्व प्राप्त करने के लिए सीमा गुणों को समायोजित कर सकते हैं।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में किसी विशिष्ट पृष्ठ पर समूहीकृत चेकबॉक्स कैसे जोड़ूं?

उ: पीडीएफ दस्तावेज़ में किसी विशिष्ट पृष्ठ पर समूहीकृत चेकबॉक्स जोड़ने के लिए, आपको तुरंत चालू करने की आवश्यकता है`RadioButtonField` तर्क के रूप में वांछित पृष्ठ संख्या वाली वस्तु। फिर, बनाएं`RadioButtonOptionField` प्रत्येक रेडियो बटन विकल्प का प्रतिनिधित्व करने वाली वस्तुएं और उनका उपयोग करके अपनी स्थिति निर्दिष्ट करें`Rectangle` वस्तु। अंत में, इन विकल्पों को इसमें जोड़ें`RadioButtonField` और जोड़ने से पहले आवश्यकतानुसार उनके स्वरूप को अनुकूलित करें`RadioButtonField` दस्तावेज़ प्रपत्र के लिए.

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ में चेकबॉक्स के कई समूह जोड़ सकता हूँ?

 उ: हां, आप एक ही पीडीएफ दस्तावेज़ में चेकबॉक्स के कई समूह जोड़ सकते हैं। प्रत्येक समूह में एक अद्वितीय होना चाहिए`RadioButtonField` वस्तु, और`RadioButtonOptionField` प्रत्येक समूह के भीतर वस्तुओं को एक ही पृष्ठ और उनके विकल्पों के लिए अद्वितीय नाम साझा करने चाहिए। यह सुनिश्चित करता है कि प्रत्येक समूह के रेडियो बटन सही ढंग से काम करते हैं, और चयन परस्पर अनन्य हैं।

#### प्रश्न: क्या समूहीकृत चेकबॉक्स सभी पीडीएफ दर्शकों और अनुप्रयोगों में समर्थित हैं?

उ: हां, समूहीकृत चेकबॉक्स सभी मानक-अनुपालक पीडीएफ व्यूअर और एप्लिकेशन में समर्थित हैं। पीडीएफ विनिर्देश रेडियो बटन और उनके समूहीकरण व्यवहार को परिभाषित करता है, जिससे उन्हें पीडीएफ प्रारूप में सार्वभौमिक रूप से मान्यता प्राप्त होती है। हालाँकि, विभिन्न प्लेटफार्मों पर सुसंगत व्यवहार सुनिश्चित करने के लिए विभिन्न पीडीएफ दर्शकों में कार्यक्षमता का परीक्षण करना आवश्यक है।