---
title: पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक
linktitle: पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छिपे हुए टेक्स्ट ब्लॉक बनाने का तरीका जानें।
type: docs
weight: 230
url: /hi/net/programming-with-text/hidden-text-block/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF फ़ाइल में छिपा हुआ टेक्स्ट ब्लॉक कैसे बनाया जाता है। छिपा हुआ टेक्स्ट ब्लॉक एक फ़्लोटिंग टेक्स्ट होता है जो तब दिखाई देता है जब माउस कर्सर किसी विशिष्ट क्षेत्र पर होवर करता है। हम दिए गए C# स्रोत कोड का उपयोग करके छिपे हुए टेक्स्ट ब्लॉक को बनाने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आप जेनरेट की गई पीडीएफ फाइल को सेव करना चाहते हैं।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपने इच्छित निर्देशिका के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नमूना दस्तावेज़ बनाएँ

इस चरण में, हम एक नमूना पीडीएफ दस्तावेज़ बनाते हैं और उसमें एक टेक्स्ट फ़्रैगमेंट जोड़ते हैं। टेक्स्ट फ़्रैगमेंट छिपे हुए टेक्स्ट ब्लॉक को प्रदर्शित करने के लिए ट्रिगर के रूप में काम करेगा।

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## चरण 3: दस्तावेज़ खोलें

 अब, हम पहले से बनाए गए दस्तावेज़ को खोलते हैं`Document` कक्षा।

```csharp
Document document = new Document(outputFile);
```

## चरण 4: पाठ का अंश ढूंढें

 हम एक का उपयोग करते हैं`TextFragmentAbsorber`ऑब्जेक्ट का उपयोग करके उस टेक्स्ट फ़्रैगमेंट को ढूँढ़ें जो छिपे हुए टेक्स्ट ब्लॉक के डिस्प्ले को ट्रिगर करेगा। इस मामले में, हम सटीक टेक्स्ट "फ़्लोटिंग टेक्स्ट प्रदर्शित करने के लिए माउस कर्सर को यहाँ ले जाएँ" की खोज कर रहे हैं।

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## चरण 5: छिपा हुआ टेक्स्ट फ़ील्ड बनाएँ

 हम एक बनाते हैं`TextBoxField` छिपे हुए टेक्स्ट फ़ील्ड को दर्शाने के लिए ऑब्जेक्ट। इस फ़ील्ड में वह टेक्स्ट होगा जो ट्रिगर टेक्स्ट पर माउस कर्सर घुमाने पर दिखाई देता है।

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

हम दस्तावेज़ के फ़ॉर्म संग्रह में छिपे हुए टेक्स्ट फ़ील्ड को जोड़ते हैं।

```csharp
document.Form.Add(floatingField);
```

## चरण 7: अदृश्य बटन बनाएं

हम एक अदृश्य बटन फ़ील्ड बनाते हैं जो ट्रिगर टेक्स्ट फ़्रैगमेंट के शीर्ष पर स्थित होगा। इस बटन फ़ील्ड में माउस एंटर और एग्ज़िट इवेंट से जुड़ी क्रियाएँ होंगी।

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## चरण 8: दस्तावेज़ सहेजें

अंत में, हम संशोधित दस्तावेज़ को छिपे हुए पाठ ब्लॉक के साथ सहेजते हैं।

```csharp
document. Save(outputFile);
```

### .NET के लिए Aspose.PDF का उपयोग करके छिपे हुए टेक्स्ट ब्लॉक के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// पाठ के साथ नमूना दस्तावेज़ बनाएँ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// पाठ सहित दस्तावेज़ खोलें
Document document = new Document(outputFile);
//नियमित अभिव्यक्ति से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएं
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// दस्तावेज़ पृष्ठों के लिए अवशोषक स्वीकार करें
document.Pages.Accept(absorber);
// पहला निकाला गया पाठ अंश प्राप्त करें
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//पृष्ठ के निर्दिष्ट आयत में फ़्लोटिंग टेक्स्ट के लिए छिपा हुआ टेक्स्ट फ़ील्ड बनाएँ
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// फ़ील्ड मान के रूप में प्रदर्शित होने वाला टेक्स्ट सेट करें
floatingField.Value = "This is the \"floating text field\".";
// हम इस परिदृश्य के लिए फ़ील्ड को 'readonly' बनाने की अनुशंसा करते हैं
floatingField.ReadOnly = true;
// दस्तावेज़ खोलते समय फ़ील्ड को अदृश्य बनाने के लिए 'hidden' फ्लैग सेट करें
floatingField.Flags |= AnnotationFlags.Hidden;
// अद्वितीय फ़ील्ड नाम सेट करना आवश्यक नहीं है, लेकिन इसकी अनुमति है
floatingField.PartialName = "FloatingField_1";
// फ़ील्ड उपस्थिति की विशेषताओं को सेट करना आवश्यक नहीं है, लेकिन यह इसे बेहतर बनाता है
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
// निर्दिष्ट फ़ील्ड (एनोटेशन) और अदृश्यता ध्वज के लिए नई छिपाने की क्रिया बनाएँ।
// (यदि आपने ऊपर इसका उल्लेख किया है तो आप फ्लोटिंग फील्ड को उसके नाम से भी संदर्भित कर सकते हैं।)
// अदृश्य बटन फ़ील्ड पर माउस के प्रवेश/निकास पर क्रियाएँ जोड़ें
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// दस्तावेज़ में बटन फ़ील्ड जोड़ें
document.Form.Add(buttonField);
// दस्तावेज़ सहेजें
document.Save(outputFile);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.PDF for .NET लाइब्रेरी का उपयोग करके एक छिपा हुआ टेक्स्ट ब्लॉक कैसे बनाया जाता है। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक छिपे हुए टेक्स्ट फ़ील्ड के साथ एक पीडीएफ दस्तावेज़ बना सकते हैं जो तब दिखाई देता है जब माउस कर्सर किसी विशिष्ट क्षेत्र पर होवर करता है। आप अपनी आवश्यकताओं के अनुसार छिपे हुए टेक्स्ट ब्लॉक की उपस्थिति और व्यवहार को अनुकूलित कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में छिपा टेक्स्ट ब्लॉक" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक" ट्यूटोरियल बताता है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में छिपा हुआ टेक्स्ट ब्लॉक कैसे बनाया जाए। छिपा हुआ टेक्स्ट ब्लॉक एक फ्लोटिंग टेक्स्ट होता है जो तब दिखाई देता है जब माउस कर्सर किसी विशिष्ट क्षेत्र पर होवर करता है। यह ट्यूटोरियल C# सोर्स कोड का उपयोग करके चरण-दर-चरण मार्गदर्शिका प्रदान करता है।

#### प्रश्न: मैं पीडीएफ फाइल में छुपा हुआ टेक्स्ट ब्लॉक क्यों बनाना चाहूंगा?

उत्तर: एक छिपा हुआ टेक्स्ट ब्लॉक बनाना इंटरैक्टिव पीडीएफ दस्तावेजों के लिए उपयोगी हो सकता है, जहां आप अतिरिक्त जानकारी या संदर्भ प्रदान करना चाहते हैं जो केवल तभी दिखाई देता है जब कोई उपयोगकर्ता अपने माउस कर्सर को निर्दिष्ट क्षेत्र पर घुमाता है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे स्थापित करूँ?

उत्तर: दस्तावेज़ निर्देशिका सेट अप करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका का पथ वाला वेरिएबल जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं।

#### प्रश्न: मैं नमूना दस्तावेज़ कैसे बनाऊं और उसमें पाठ अंश कैसे जोड़ूं?

 उत्तर: ट्यूटोरियल में, आप इसका उपयोग करते हैं`Document` क्लास का उपयोग करके सैंपल पीडीएफ दस्तावेज़ बनाएँ और टेक्स्ट फ़्रैगमेंट जोड़ें। यह टेक्स्ट फ़्रैगमेंट छिपे हुए टेक्स्ट ब्लॉक को प्रदर्शित करने के लिए ट्रिगर के रूप में कार्य करता है।

#### प्रश्न: मैं उस पाठ खंड को कैसे ढूंढूं जो छिपे हुए पाठ ब्लॉक को ट्रिगर करता है?

 उत्तर: ट्यूटोरियल दर्शाता है कि इसका उपयोग कैसे किया जाता है`TextFragmentAbsorber` ऑब्जेक्ट उस टेक्स्ट फ़्रैगमेंट को ढूँढ़ता है जो छिपे हुए टेक्स्ट ब्लॉक के डिस्प्ले को ट्रिगर करता है। यह PDF दस्तावेज़ के भीतर एक विशिष्ट टेक्स्ट स्ट्रिंग की खोज करता है।

#### प्रश्न: मैं छुपे हुए टेक्स्ट फ़ील्ड को कैसे बनाऊं और अनुकूलित करूं?

 उत्तर: आप एक`TextBoxField`छिपे हुए टेक्स्ट फ़ील्ड का प्रतिनिधित्व करने के लिए ऑब्जेक्ट। ट्यूटोरियल छिपे हुए टेक्स्ट फ़ील्ड की स्थिति, मान, उपस्थिति और व्यवहार जैसे विभिन्न गुणों को सेट करने के लिए कोड प्रदान करता है।

#### प्रश्न: मैं छिपे हुए टेक्स्ट ब्लॉक से संबद्ध अदृश्य बटन कैसे बनाऊं?

 उत्तर: एक अदृश्य बटन फ़ील्ड का निर्माण किया जाता है`ButtonField` क्लास। यह बटन फ़ील्ड ट्रिगर टेक्स्ट फ़्रैगमेंट के शीर्ष पर स्थित है और इसमें माउस एंटर और एग्ज़िट इवेंट से जुड़ी क्रियाएँ हैं। ये क्रियाएँ छिपे हुए टेक्स्ट ब्लॉक की दृश्यता को नियंत्रित करती हैं।

#### प्रश्न: क्या मैं छिपे हुए टेक्स्ट ब्लॉक और ट्रिगर क्षेत्र के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हां, आप छिपे हुए टेक्स्ट फ़ील्ड और अदृश्य बटन दोनों के विभिन्न गुणों को अनुकूलित कर सकते हैं, जिसमें फ़ॉन्ट, रंग, आकार और स्थिति शामिल हैं।

#### प्रश्न: मैं संशोधित दस्तावेज़ को छिपे हुए पाठ ब्लॉक के साथ कैसे सहेजूँ?

 उत्तर: ट्यूटोरियल दर्शाता है कि संशोधित दस्तावेज़ को कैसे सहेजा जाए`Save` की विधि`Document` कक्षा।