---
title: प्रपत्र फ़ील्ड ले जाएँ
linktitle: प्रपत्र फ़ील्ड ले जाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ अपने PDF दस्तावेज़ों में फ़ॉर्म फ़ील्ड को आसानी से इधर-उधर ले जाएँ।
type: docs
weight: 200
url: /hi/net/programming-with-forms/move-form-field/
---
इस ट्यूटोरियल में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में फॉर्म फ़ील्ड को कैसे स्थानांतरित किया जाए। इस प्रक्रिया में आपका मार्गदर्शन करने के लिए हम चरण दर चरण C# स्रोत कोड की व्याख्या करेंगे।

## चरण 1: तैयारी

सुनिश्चित करें कि आपने आवश्यक लाइब्रेरीज़ आयात कर ली हैं और अपनी दस्तावेज़ निर्देशिका के लिए पथ निर्धारित कर लिया है:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें

मौजूदा पीडीएफ दस्तावेज़ लोड करें:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## चरण 3: फॉर्म फ़ील्ड प्राप्त करें

वह प्रपत्र फ़ील्ड प्राप्त करें जिसे आप स्थानांतरित करना चाहते हैं:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## चरण 4: फ़ील्ड स्थान बदलें

एक नए आयताकार क्षेत्र को परिभाषित करके प्रपत्र फ़ील्ड का स्थान बदलें:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## चरण 5: संपादित दस्तावेज़ सहेजें

संशोधित पीडीएफ दस्तावेज़ सहेजें:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके फॉर्म फ़ील्ड को स्थानांतरित करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// एक फ़ील्ड प्राप्त करें
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// फ़ील्ड स्थान संशोधित करें
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// संशोधित दस्तावेज़ सहेजें
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में फॉर्म फ़ील्ड को कैसे स्थानांतरित किया जाए। इन चरणों का पालन करके, आप आसानी से किसी विशिष्ट फ़ील्ड पर नेविगेट कर सकते हैं और आवश्यकतानुसार उसका स्थान बदल सकते हैं।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके एक ही PDF दस्तावेज़ में एकाधिक फॉर्म फ़ील्ड को स्थानांतरित कर सकता हूँ?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके एक ही पीडीएफ दस्तावेज़ में एकाधिक फॉर्म फ़ील्ड को स्थानांतरित कर सकते हैं। बस उस प्रत्येक फॉर्म फ़ील्ड के लिए प्रक्रिया दोहराएं जिसे आप स्थानांतरित करना चाहते हैं।

#### प्रश्न: क्या फॉर्म फ़ील्ड को स्थानांतरित करने से उससे संबंधित डेटा या कार्यक्षमता प्रभावित होगी?

उ: नहीं, किसी प्रपत्र फ़ील्ड को स्थानांतरित करने से उससे संबंधित डेटा या कार्यक्षमता प्रभावित नहीं होती है। किसी नए स्थान पर ले जाने के बाद प्रपत्र फ़ील्ड अपने सभी गुणों और मूल्यों को बरकरार रखता है।

#### प्रश्न: मैं प्रपत्र फ़ील्ड के नए स्थान के लिए सटीक निर्देशांक कैसे निर्धारित कर सकता हूं?

 उ: आप इसका उपयोग करके नया स्थान निर्दिष्ट कर सकते हैं`Aspose.Pdf.Rectangle` वर्ग, जहां आप ऊपरी-बाएँ कोने के X और Y निर्देशांक और आयताकार क्षेत्र के निचले-दाएँ कोने के X और Y निर्देशांक को परिभाषित करते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF विंडोज़ और लिनक्स दोनों वातावरणों के साथ संगत है?

उत्तर: हां, .NET के लिए Aspose.PDF विंडोज और लिनक्स दोनों वातावरणों के साथ संगत है, जो डेवलपर्स को उनके पसंदीदा ऑपरेटिंग सिस्टम में काम करने के लिए लचीलापन प्रदान करता है।