---
title: पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक
linktitle: पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छिपे हुए टेक्स्ट ब्लॉक बनाना सीखें।
type: docs
weight: 230
url: /hi/net/programming-with-text/hidden-text-block/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में एक छिपा हुआ टेक्स्ट ब्लॉक कैसे बनाया जाए। एक छिपा हुआ टेक्स्ट ब्लॉक एक फ्लोटिंग टेक्स्ट होता है जो तब दिखाई देता है जब माउस कर्सर एक विशिष्ट क्षेत्र पर घूमता है। हम दिए गए C# स्रोत कोड का उपयोग करके छिपे हुए टेक्स्ट ब्लॉक को बनाने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित किया गया।
- C# प्रोग्रामिंग की बुनियादी समझ।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस निर्देशिका के लिए पथ सेट करना होगा जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir`आपकी वांछित निर्देशिका के पथ के साथ परिवर्तनीय।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नमूना दस्तावेज़ बनाएँ

इस चरण में, हम एक नमूना पीडीएफ दस्तावेज़ बनाते हैं और उसमें एक टेक्स्ट टुकड़ा जोड़ते हैं। टेक्स्ट खंड छिपे हुए टेक्स्ट ब्लॉक को प्रदर्शित करने के लिए ट्रिगर के रूप में काम करेगा।

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## चरण 3: दस्तावेज़ खोलें

 अब, हम पहले बनाए गए दस्तावेज़ को का उपयोग करके खोलते हैं`Document` कक्षा।

```csharp
Document document = new Document(outputFile);
```

## चरण 4: टेक्स्ट फ़्रैगमेंट ढूंढें

 हम एक का उपयोग करते हैं`TextFragmentAbsorber` टेक्स्ट खंड को खोजने के लिए ऑब्जेक्ट का उपयोग करें जो छिपे हुए टेक्स्ट ब्लॉक के प्रदर्शन को ट्रिगर करेगा। इस मामले में, हम सटीक टेक्स्ट "फ़्लोटिंग टेक्स्ट प्रदर्शित करने के लिए माउस कर्सर को यहां ले जाएं" खोज रहे हैं।

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## चरण 5: हिडन टेक्स्ट फ़ील्ड बनाएं

 हम एक बनाते हैं`TextBoxField` छुपे हुए टेक्स्ट फ़ील्ड का प्रतिनिधित्व करने के लिए ऑब्जेक्ट। इस फ़ील्ड में वह टेक्स्ट होगा जो तब दिखाई देता है जब माउस कर्सर ट्रिगर टेक्स्ट पर घूमता है।

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## चरण 6: दस्तावेज़ में छिपा हुआ टेक्स्ट फ़ील्ड जोड़ें

हम दस्तावेज़ के प्रपत्र संग्रह में छिपे हुए टेक्स्ट फ़ील्ड को जोड़ते हैं।

```csharp
document.Form.Add(floatingField);
```

## चरण 7: अदृश्य बटन बनाएं

हम एक अदृश्य बटन फ़ील्ड बनाते हैं जो ट्रिगर टेक्स्ट खंड के शीर्ष पर स्थित होगा। इस बटन फ़ील्ड में माउस प्रवेश और निकास ईवेंट से संबंधित क्रियाएं होंगी।

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## चरण 8: दस्तावेज़ सहेजें

अंत में, हम संशोधित दस्तावेज़ को छिपे हुए टेक्स्ट ब्लॉक के साथ सहेजते हैं।

```csharp
document. Save(outputFile);
```

### .NET के लिए Aspose.PDF का उपयोग करके हिडन टेक्स्ट ब्लॉक के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// पाठ के साथ नमूना दस्तावेज़ बनाएँ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// पाठ के साथ दस्तावेज़ खोलें
Document document = new Document(outputFile);
// रेगुलर एक्सप्रेशन से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए टेक्स्टएब्जॉर्बर ऑब्जेक्ट बनाएं
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// दस्तावेज़ पृष्ठों के लिए अवशोषक स्वीकार करें
document.Pages.Accept(absorber);
// पहला निकाला गया पाठ खंड प्राप्त करें
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// पृष्ठ के निर्दिष्ट आयत में फ़्लोटिंग टेक्स्ट के लिए छिपा हुआ टेक्स्ट फ़ील्ड बनाएं
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// टेक्स्ट को फ़ील्ड मान के रूप में प्रदर्शित करने के लिए सेट करें
floatingField.Value = "This is the \"floating text field\".";
// हम इस परिदृश्य के लिए फ़ील्ड को 'केवल पढ़ने योग्य' बनाने की अनुशंसा करते हैं
floatingField.ReadOnly = true;
// दस्तावेज़ खोलने पर फ़ील्ड को अदृश्य बनाने के लिए 'छिपा हुआ' ध्वज सेट करें
floatingField.Flags |= AnnotationFlags.Hidden;
// एक अद्वितीय फ़ील्ड नाम सेट करना आवश्यक नहीं है लेकिन इसकी अनुमति है
floatingField.PartialName = "FloatingField_1";
// फ़ील्ड उपस्थिति की विशेषताएँ निर्धारित करना आवश्यक नहीं है, लेकिन यह इसे बेहतर बनाता है
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// दस्तावेज़ में टेक्स्ट फ़ील्ड जोड़ें
document.Form.Add(floatingField);
// पाठ खंड स्थिति पर अदृश्य बटन बनाएं
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// निर्दिष्ट फ़ील्ड (एनोटेशन) और अदृश्यता ध्वज के लिए नई छिपाने की क्रिया बनाएं।
//(यदि आपने इसे ऊपर निर्दिष्ट किया है तो आप फ़्लोटिंग फ़ील्ड को नाम से भी संदर्भित कर सकते हैं।)
// अदृश्य बटन फ़ील्ड में माउस एंटर/एग्जिट पर क्रियाएँ जोड़ें
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// दस्तावेज़ में बटन फ़ील्ड जोड़ें
document.Form.Add(buttonField);
// दस्तावेज़ सहेजें
document.Save(outputFile);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके एक छिपा हुआ टेक्स्ट ब्लॉक कैसे बनाया जाता है। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक छिपे हुए टेक्स्ट फ़ील्ड के साथ एक पीडीएफ दस्तावेज़ तैयार कर सकते हैं जो तब दिखाई देता है जब माउस कर्सर एक विशिष्ट क्षेत्र पर घूमता है। आप अपनी आवश्यकताओं के अनुसार छिपे हुए टेक्स्ट ब्लॉक की उपस्थिति और व्यवहार को अनुकूलित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में हिडन टेक्स्ट ब्लॉक" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक" ट्यूटोरियल बताता है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में एक छिपा हुआ टेक्स्ट ब्लॉक कैसे बनाया जाए। एक छिपा हुआ टेक्स्ट ब्लॉक एक फ्लोटिंग टेक्स्ट होता है जो तब दिखाई देता है जब माउस कर्सर एक विशिष्ट क्षेत्र पर घूमता है। यह ट्यूटोरियल C# स्रोत कोड का उपयोग करके चरण-दर-चरण मार्गदर्शिका प्रदान करता है।

#### प्रश्न: मैं पीडीएफ फाइल में एक छिपा हुआ टेक्स्ट ब्लॉक क्यों बनाना चाहूंगा?

उ: एक छिपा हुआ टेक्स्ट ब्लॉक बनाना इंटरैक्टिव पीडीएफ दस्तावेजों के लिए उपयोगी हो सकता है जहां आप अतिरिक्त जानकारी या संदर्भ प्रदान करना चाहते हैं जो केवल तब दिखाई देता है जब कोई उपयोगकर्ता अपने माउस कर्सर को निर्दिष्ट क्षेत्र पर घुमाता है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे सेट करूँ?

उ: दस्तावेज़ निर्देशिका स्थापित करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका के पथ के साथ वैरिएबल जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं।

#### प्रश्न: मैं एक नमूना दस्तावेज़ कैसे बनाऊं और उसमें एक पाठ खंड कैसे जोड़ूं?

उत्तर: ट्यूटोरियल में, आप इसका उपयोग करते हैं`Document` एक नमूना पीडीएफ दस्तावेज़ बनाने और एक पाठ खंड जोड़ने के लिए कक्षा। यह टेक्स्ट खंड छिपे हुए टेक्स्ट ब्लॉक को प्रदर्शित करने के लिए ट्रिगर के रूप में कार्य करता है।

#### प्रश्न: मैं उस टेक्स्ट खंड को कैसे ढूंढूं जो छिपे हुए टेक्स्ट ब्लॉक को ट्रिगर करता है?

 ए: ट्यूटोरियल दर्शाता है कि ए का उपयोग कैसे करें`TextFragmentAbsorber` टेक्स्ट खंड को ढूंढने के लिए ऑब्जेक्ट का उपयोग करें जो छिपे हुए टेक्स्ट ब्लॉक के प्रदर्शन को ट्रिगर करता है। यह पीडीएफ दस्तावेज़ के भीतर एक विशिष्ट टेक्स्ट स्ट्रिंग की खोज करता है।

#### प्रश्न: मैं छिपे हुए टेक्स्ट फ़ील्ड को कैसे बना और अनुकूलित कर सकता हूँ?

 ए: आप एक बनाते हैं`TextBoxField` छुपे हुए टेक्स्ट फ़ील्ड का प्रतिनिधित्व करने के लिए ऑब्जेक्ट। ट्यूटोरियल छिपे हुए टेक्स्ट फ़ील्ड की स्थिति, मूल्य, उपस्थिति और व्यवहार जैसे विभिन्न गुणों को सेट करने के लिए कोड प्रदान करता है।

#### प्रश्न: मैं छिपे हुए टेक्स्ट ब्लॉक से जुड़ा एक अदृश्य बटन कैसे बनाऊं?

 उ: का उपयोग करके एक अदृश्य बटन फ़ील्ड बनाई जाती है`ButtonField` कक्षा। यह बटन फ़ील्ड ट्रिगर टेक्स्ट खंड के शीर्ष पर स्थित है और इसमें माउस दर्ज करने और बाहर निकलने की घटनाओं से जुड़ी क्रियाएं हैं। ये क्रियाएं छिपे हुए टेक्स्ट ब्लॉक की दृश्यता को नियंत्रित करती हैं।

#### प्रश्न: क्या मैं छिपे हुए टेक्स्ट ब्लॉक और ट्रिगर क्षेत्र की उपस्थिति को अनुकूलित कर सकता हूँ?

उ: हां, आप फ़ॉन्ट, रंग, आकार और स्थिति सहित छिपे हुए टेक्स्ट फ़ील्ड और अदृश्य बटन दोनों के विभिन्न गुणों को अनुकूलित कर सकते हैं।

#### प्रश्न: मैं संशोधित दस्तावेज़ को छिपे हुए टेक्स्ट ब्लॉक के साथ कैसे सहेजूँ?

 उ: ट्यूटोरियल दर्शाता है कि इसका उपयोग करके संशोधित दस्तावेज़ को कैसे सहेजा जाए`Save` की विधि`Document` कक्षा।