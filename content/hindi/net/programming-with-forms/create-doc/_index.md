---
title: दस्तावेज़ बनाएँ
linktitle: दस्तावेज़ बनाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके आसानी से रेडियो बटन के साथ एक दस्तावेज़ बनाएं।
type: docs
weight: 40
url: /hi/net/programming-with-forms/create-doc/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन के साथ एक दस्तावेज़ कैसे बनाया जाए। इस प्रक्रिया में आपका मार्गदर्शन करने के लिए हम चरण दर चरण C# स्रोत कोड की व्याख्या करेंगे।

##चरण 1: तैयारी

सबसे पहले, सुनिश्चित करें कि आपने आवश्यक पुस्तकालयों को आयात कर लिया है और दस्तावेज़ निर्देशिका के लिए पथ निर्धारित कर दिया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ बनाएँ

पीडीएफ दस्तावेज़ को रखने के लिए एक नया दस्तावेज़ ऑब्जेक्ट बनाएं:

```csharp
Document doc = new Document();
```

## चरण 3: एक पेज जोड़ें

दस्तावेज़ में एक नया पृष्ठ जोड़ें:

```csharp
Page page = doc.Pages.Add();
```

## चरण 4: एक रेडियो बटन फ़ील्ड जोड़ें

एक रेडियो बटन फ़ील्ड बनाएं और उसकी स्थिति और आकार निर्धारित करें:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## चरण 5: रेडियो बटन विकल्प जोड़ें

रेडियो बटन फ़ील्ड में वांछित विकल्प जोड़ें। आप आवश्यकतानुसार प्रत्येक विकल्प के निर्देशांक और आकार निर्धारित कर सकते हैं:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## चरण 6: फॉर्म में रेडियो बटन फ़ील्ड जोड़ें

दस्तावेज़ प्रपत्र फ़ील्ड संग्रह में रेडियो बटन फ़ील्ड जोड़ें:

```csharp
doc.Form.Add(field);
```

## चरण 7: दस्तावेज़ सहेजें

पीडीएफ दस्तावेज़ सहेजें:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके दस्तावेज़ बनाने के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// एक नया दस्तावेज़ बनाएँ
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// रेडियो बटन फ़ील्ड जोड़ें
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// रेडियो बटन विकल्प जोड़ें. कृपया ध्यान दें कि ये विकल्प स्थित हैं
	// न तो क्षैतिज रूप से और न ही लंबवत रूप से.
	// आप उनके लिए कोई भी निर्देशांक (और आकार भी) सेट करने का प्रयास कर सकते हैं।
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// पीडीएफ दस्तावेज़ सहेजें
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन के साथ एक दस्तावेज़ कैसे बनाया जाए। इन चरणों का पालन करके, आप Aspose.PDF का उपयोग करके आसानी से अपने पीडीएफ दस्तावेज़ों में रेडियो बटन जोड़ सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके दस्तावेज़ में रेडियो बटन की उपस्थिति को अनुकूलित कर सकता हूँ?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके दस्तावेज़ में रेडियो बटन की उपस्थिति को अनुकूलित कर सकते हैं। आप रेडियो बटन के स्वरूप को अनुकूलित करने के लिए आकार, रंग, बॉर्डर शैली और बहुत कुछ जैसे गुण सेट कर सकते हैं।

#### प्रश्न: मैं परस्पर अनन्य विकल्पों के साथ रेडियो बटन समूह कैसे जोड़ सकता हूँ?

उ: परस्पर अनन्य विकल्प बनाने के लिए, आप एक ही नाम से कई रेडियो बटन फ़ील्ड जोड़ सकते हैं। इससे यह सुनिश्चित हो जाएगा कि जब एक विकल्प चुना जाता है, तो उसी नाम वाले अन्य विकल्प स्वचालित रूप से अचयनित हो जाएंगे।

#### प्रश्न: क्या रेडियो बटनों के लिए डिफ़ॉल्ट चयनित विकल्प सेट करना संभव है?

उ: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन के लिए एक डिफ़ॉल्ट चयनित विकल्प सेट कर सकते हैं। आप इसका उपयोग कर सकते हैं`Selected` की संपत्ति`RadioButtonOptionField` किसी विकल्प को डिफ़ॉल्ट रूप से चयनित के रूप में चिह्नित करने के लिए ऑब्जेक्ट।

#### प्रश्न: क्या मैं रेडियो बटन में ईवेंट हैंडलर जोड़ सकता हूँ?

 उ: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन में ईवेंट हैंडलर जोड़ सकते हैं। आप जावास्क्रिप्ट क्रियाओं को संबद्ध कर सकते हैं, जैसे कि`OnValueChanged`, जब उपयोगकर्ता कोई विकल्प चुनता है तो विशिष्ट क्रियाएं करने के लिए रेडियो बटन पर।

#### प्रश्न: उपयोगकर्ता द्वारा चयन करने के बाद मैं रेडियो बटन समूह से चयनित विकल्प को कैसे पुनः प्राप्त कर सकता हूं?

 उ: आप .NET के लिए Aspose.PDF का उपयोग करके रेडियो बटन समूह से चयनित विकल्प पुनः प्राप्त कर सकते हैं। उपयोगकर्ता द्वारा चयन करने के बाद, आप उस तक पहुंच सकते हैं`Selected` की संपत्ति`RadioButtonOptionField` यह जांचने के लिए ऑब्जेक्ट करें कि कौन सा विकल्प चुना गया है।