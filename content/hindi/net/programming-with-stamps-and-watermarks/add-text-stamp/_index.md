---
title: पीडीएफ फाइल में टेक्स्ट स्टैम्प जोड़ें
linktitle: पीडीएफ फाइल में टेक्स्ट स्टैम्प जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ PDF फ़ाइल में आसानी से टेक्स्ट स्टैम्प जोड़ने का तरीका जानें।
type: docs
weight: 50
url: /hi/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
इस ट्यूटोरियल में, हम आपको चरण दर चरण बताएंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में टेक्स्ट स्टैम्प कैसे जोड़ा जाए। हम आपको दिखाएंगे कि पीडीएफ फ़ाइल के एक विशिष्ट पृष्ठ पर एक कस्टम टेक्स्ट स्टैम्प जोड़ने के लिए दिए गए C# स्रोत कोड का उपयोग कैसे करें।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- एक स्थापित .NET विकास वातावरण।
- .NET के लिए Aspose.PDF लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में संदर्भित की गई।

## चरण 2: पीडीएफ दस्तावेज़ लोड हो रहा है

पहला कदम मौजूदा पीडीएफ दस्तावेज़ को अपने प्रोजेक्ट में लोड करना है। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"आपकी दस्तावेज़ निर्देशिका" को उस निर्देशिका के वास्तविक पथ से बदलना सुनिश्चित करें जहां आपका पीडीएफ दस्तावेज़ स्थित है।

## चरण 3: टेक्स्ट बफ़र बनाना

अब जब आपने पीडीएफ दस्तावेज़ अपलोड कर दिया है, तो आप जोड़ने के लिए टेक्स्ट स्टैम्प बना सकते हैं। इसे करने का तरीका यहां बताया गया है:

```csharp
// टेक्स्ट बफ़र बनाएं
TextStamp textStamp = new TextStamp("Example Stamp");
```

उपरोक्त कोड एक नया टेक्स्ट बफ़र बनाता है जिसमें निर्दिष्ट टेक्स्ट होता है।

## चरण 4: टेक्स्ट स्टाम्प गुणों को कॉन्फ़िगर करना

पीडीएफ दस्तावेज़ में टेक्स्ट स्टैम्प जोड़ने से पहले, आप स्टैम्प के विभिन्न गुणों को कॉन्फ़िगर कर सकते हैं, जैसे पृष्ठभूमि, स्थिति, रोटेशन, फ़ॉन्ट, आकार, आदि। यहां बताया गया है:

```csharp
// टेक्स्ट बफ़र गुण कॉन्फ़िगर करें
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

आप इन संपत्तियों को अपनी आवश्यकताओं के अनुसार समायोजित कर सकते हैं।

## चरण 5: पीडीएफ में टेक्स्ट स्टैम्प जोड़ें

अब जब टेक्स्ट स्टैम्प तैयार हो गया है, तो आप इसे पीडीएफ दस्तावेज़ के एक विशिष्ट पृष्ठ में जोड़ सकते हैं। ऐसे:

```csharp
//विशिष्ट पृष्ठ पर टेक्स्ट बफ़र जोड़ें
pdfDocument.Pages[1].AddStamp(textStamp);
```

उपरोक्त कोड पीडीएफ दस्तावेज़ के पहले पृष्ठ पर टेक्स्ट स्टैम्प जोड़ता है। यदि आवश्यक हो तो आप कोई अन्य पृष्ठ निर्दिष्ट कर सकते हैं.

## चरण 6: आउटपुट दस्तावेज़ सहेजें

एक बार जब आप टेक्स्ट स्टैम्प जोड़ लेते हैं, तो आप संपादित पीडीएफ दस्तावेज़ को सहेज सकते हैं। ऐसे:

```csharp
// आउटपुट दस्तावेज़ सहेजें
pdfDocument.Save(dataDir);
```

उपरोक्त कोड संशोधित पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजता है।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट स्टैम्प जोड़ने के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// टेक्स्ट स्टैम्प बनाएं
TextStamp textStamp = new TextStamp("Sample Stamp");

// सेट करें कि स्टाम्प पृष्ठभूमि है या नहीं
textStamp.Background = true;

// मूल निर्धारित करें
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// स्टाम्प घुमाएँ
textStamp.Rotate = Rotation.on90;

// पाठ गुण सेट करें
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// विशिष्ट पृष्ठ पर स्टाम्प जोड़ें
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// आउटपुट दस्तावेज़ सहेजें
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## निष्कर्ष

बधाई हो! आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट स्टैम्प कैसे जोड़ा जाता है। अब आप पीडीएफ दस्तावेज़ों में कस्टम टेक्स्ट स्टैम्प जोड़ने के लिए इस ज्ञान को अपनी परियोजनाओं पर लागू कर सकते हैं।

### पीडीएफ फाइल में टेक्स्ट स्टैम्प जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में टेक्स्ट स्टैम्प जोड़ने का उद्देश्य क्या है?

उ: टेक्स्ट स्टैम्प जोड़ने से आप पीडीएफ दस्तावेज़ के एक विशिष्ट पृष्ठ पर कस्टम टेक्स्ट रख सकते हैं। यह सुविधा दस्तावेज़ की सामग्री को बढ़ाने और अतिरिक्त संदर्भ प्रदान करने के लिए लेबल, टिप्पणियाँ, वॉटरमार्क, या कोई अन्य पाठ्य जानकारी जोड़ने के लिए उपयोगी है।

#### प्रश्न: क्या मैं टेक्स्ट स्टैम्प के स्वरूप को अनुकूलित कर सकता हूँ, जैसे कि फ़ॉन्ट, आकार, रंग और रोटेशन?

 उत्तर: हां, आप टेक्स्ट स्टैम्प के स्वरूप को पूरी तरह से अनुकूलित कर सकते हैं। प्रदान किया गया C# स्रोत कोड दर्शाता है कि विभिन्न गुणों को कैसे सेट किया जाए`TextStamp` ऑब्जेक्ट, जिसमें फ़ॉन्ट, फ़ॉन्ट आकार, फ़ॉन्ट शैली, टेक्स्ट रंग, पृष्ठभूमि रंग और रोटेशन शामिल हैं।

#### प्रश्न: क्या एक ही पीडीएफ दस्तावेज़ के विभिन्न पृष्ठों में एकाधिक टेक्स्ट स्टैम्प जोड़ना संभव है?

उ: बिल्कुल, आप एक ही पीडीएफ दस्तावेज़ के विभिन्न पृष्ठों में एकाधिक टेक्स्ट स्टैम्प जोड़ सकते हैं। ट्यूटोरियल का प्रदान किया गया कोड आपको टेक्स्ट स्टैम्प जोड़ने के लिए लक्ष्य पृष्ठ निर्दिष्ट करने की अनुमति देता है, जो इसे दस्तावेज़ के भीतर विभिन्न पृष्ठों के लिए बहुमुखी बनाता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में टेक्स्ट स्टांप की स्थिति कैसे निर्दिष्ट करूं?

 उत्तर: आप टेक्स्ट स्टैम्प की स्थिति को संशोधित करके अनुकूलित कर सकते हैं`XIndent` और`YIndent` के गुण`TextStamp` वस्तु। ये गुण पृष्ठ की उत्पत्ति के सापेक्ष स्टाम्प के ऊपरी-बाएँ कोने के निर्देशांक को परिभाषित करते हैं।

#### प्रश्न: क्या मैं मौजूदा पीडीएफ दस्तावेजों में टेक्स्ट स्टैम्प जोड़ने के लिए इस पद्धति को लागू कर सकता हूं?

उ: हाँ, आप टेक्स्ट स्टैम्प जोड़ने के लिए मौजूदा पीडीएफ दस्तावेजों में इस पद्धति को लागू कर सकते हैं। ट्यूटोरियल का प्रदान किया गया कोड दर्शाता है कि मौजूदा पीडीएफ दस्तावेज़ को कैसे लोड किया जाए और एक विशिष्ट पृष्ठ पर टेक्स्ट स्टैम्प कैसे जोड़ा जाए।

#### प्रश्न: क्या मैं टेक्स्ट स्टैम्प में पृष्ठभूमि और अग्रभूमि दोनों रंग जोड़ सकता हूँ?

 उत्तर: हाँ, आप टेक्स्ट स्टैम्प में पृष्ठभूमि और अग्रभूमि दोनों रंग जोड़ सकते हैं। सेटिंग करके`Background` संपत्ति को`true` , आप टेक्स्ट स्टैम्प के लिए एक रंगीन पृष्ठभूमि प्रदान कर सकते हैं। इसके अतिरिक्त, आप सेट कर सकते हैं`TextState.ForegroundColor` पाठ का रंग निर्दिष्ट करने की संपत्ति।

#### प्रश्न: मैं यह कैसे सुनिश्चित कर सकता हूं कि टेक्स्ट स्टैम्प पीडीएफ दस्तावेज़ की अंतर्निहित सामग्री को अस्पष्ट नहीं करता है?

 उ: टेक्स्ट स्टांप जोड़ते समय, उसके प्लेसमेंट का ध्यान रखें ताकि यह सुनिश्चित हो सके कि यह महत्वपूर्ण जानकारी को बाधित नहीं करता है या दस्तावेज़ की पठनीयता को नकारात्मक रूप से प्रभावित नहीं करता है। आप समायोजित कर सकते हैं`XIndent` और`YIndent` टेक्स्ट स्टैम्प को उचित रूप से स्थित करने के लिए गुण।

#### प्रश्न: क्या मैं इस पद्धति का उपयोग टेक्स्ट के अलावा चित्र या लोगो जैसे स्टैम्प जोड़ने के लिए कर सकता हूँ?

उ: यह विशिष्ट ट्यूटोरियल टेक्स्ट स्टैम्प जोड़ने पर केंद्रित है, लेकिन आप .NET के लिए Aspose.PDF का उपयोग करके इसी तरह अन्य प्रकार के स्टैम्प, जैसे चित्र या लोगो, जोड़ सकते हैं। इस प्रक्रिया में उपयुक्त स्टाम्प ऑब्जेक्ट बनाना और उसके गुणों को कॉन्फ़िगर करना शामिल है।

#### प्रश्न: मैं एकाधिक पीडीएफ दस्तावेजों में टेक्स्ट स्टैम्प जोड़ने की प्रक्रिया को कैसे स्वचालित कर सकता हूं?

उ: आप एक स्क्रिप्ट या प्रोग्राम बनाकर कई पीडीएफ दस्तावेज़ों में टेक्स्ट स्टैम्प जोड़ने की प्रक्रिया को स्वचालित कर सकते हैं जो दस्तावेज़ों की एक सूची के माध्यम से दोहराता है और प्रत्येक पर समान टेक्स्ट स्टैम्पिंग प्रक्रिया लागू करता है।