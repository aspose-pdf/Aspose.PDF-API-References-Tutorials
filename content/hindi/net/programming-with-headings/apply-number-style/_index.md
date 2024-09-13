---
title: पीडीएफ फाइल में नंबर स्टाइल लागू करें
linktitle: पीडीएफ फाइल में नंबर स्टाइल लागू करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.PDF का उपयोग करके PDF में शीर्षकों पर विभिन्न संख्या शैलियों (रोमन अंक, वर्णमाला) को लागू करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-headings/apply-number-style/
---
## परिचय

क्या आपको कभी अपने PDF दस्तावेज़ों में सुंदर क्रमांकित सूचियाँ जोड़ने की ज़रूरत महसूस हुई है? चाहे आप कानूनी दस्तावेज़, रिपोर्ट या प्रस्तुतियाँ फ़ॉर्मेट कर रहे हों, जानकारी को व्यवस्थित करने के लिए उचित क्रमांकन शैलियाँ ज़रूरी हैं। .NET के लिए Aspose.PDF के साथ, आप अपनी PDF फ़ाइल के शीर्षकों पर विभिन्न क्रमांकन शैलियाँ लागू कर सकते हैं, जिससे अच्छी तरह से संरचित और पेशेवर दस्तावेज़ बन सकते हैं। 

## आवश्यक शर्तें

कोडिंग शुरू करने से पहले, आइए जानें कि आपको क्या चाहिए होगा:

1. .NET के लिए Aspose.PDF: Aspose.PDF का नवीनतम संस्करण यहाँ से डाउनलोड करें[यहाँ](https://releases.aspose.com/pdf/net/).
2. विकास वातावरण: सुनिश्चित करें कि आपके पास Visual Studio या कोई अन्य .NET-संगत IDE है।
3. .NET फ्रेमवर्क: सुनिश्चित करें कि आपके पास .NET फ्रेमवर्क 4.0 या उच्चतर संस्करण स्थापित है।
4.  लाइसेंस: आप अस्थायी लाइसेंस का उपयोग कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) या अन्वेषण करें[मुफ्त परीक्षण](https://releases.aspose.com/) विकल्प.

## पैकेज आयात करें

आरंभ करने के लिए, सुनिश्चित करें कि आपके प्रोजेक्ट में निम्नलिखित नामस्थान आयातित हैं:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 1: दस्तावेज़ सेट करना

आइए एक नया पीडीएफ दस्तावेज़ बनाकर और उसके पेज सेटिंग कॉन्फ़िगर करके शुरू करें। हम अपनी सामग्री के लेआउट को नियंत्रित करने के लिए पेज का आकार और मार्जिन सेट करेंगे।

स्पष्टीकरण: इस चरण में, हम पीडीएफ की मूल संरचना स्थापित कर रहे हैं, जिसमें सुसंगत स्वरूपण के लिए पृष्ठ का आकार, ऊंचाई और मार्जिन को परिभाषित करना शामिल है।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// पृष्ठ आयाम और मार्जिन सेट करें
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

ऐसा करने से, आपके दस्तावेज़ का पृष्ठ आकार मानक हो जाएगा, जो 8.5 x 11 इंच के पृष्ठ के बराबर होगा, तथा सभी तरफ 72 पॉइंट (या 1 इंच) का मार्जिन होगा।

## चरण 2: पीडीएफ में पेज जोड़ना

इसके बाद, हम पीडीएफ दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे जहां हम बाद में नंबरिंग शैलियाँ लागू करेंगे।

स्पष्टीकरण: प्रत्येक PDF को पृष्ठों की आवश्यकता होती है! यह चरण PDF में एक रिक्त पृष्ठ जोड़ता है और दस्तावेज़-स्तरीय सेटिंग्स से मेल खाने के लिए इसके मार्जिन को सेट करता है।

```csharp
// PDF दस्तावेज़ में नया पृष्ठ जोड़ें
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## चरण 3: एक फ़्लोटिंग बॉक्स बनाएं

फ़्लोटिंगबॉक्स आपको सामग्री (जैसे टेक्स्ट या शीर्षक) को एक बॉक्स के अंदर रखने की अनुमति देता है जो पृष्ठ के प्रवाह से स्वतंत्र रूप से व्यवहार करता है। यह तब उपयोगी होता है जब आप अपनी सामग्री के लेआउट पर पूर्ण नियंत्रण चाहते हैं।

स्पष्टीकरण: यहां, हम उन शीर्षकों को शामिल करने के लिए एक फ्लोटिंगबॉक्स स्थापित कर रहे हैं जिन पर संख्या शैलियाँ लागू होंगी।

```csharp
// संरचित सामग्री के लिए फ़्लोटिंगबॉक्स बनाएँ
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## चरण 4: रोमन अंकों के साथ पहला शीर्षक जोड़ें

अब आता है रोमांचक हिस्सा! चलिए पहले शीर्षक में लोअर-केस रोमन अंक जोड़ते हैं।

स्पष्टीकरण: हम शीर्षक पर NumberingStyle.NumeralsRomanLowercase शैली लागू कर रहे हैं, जो रोमन अंकों (i, ii, iii, आदि) में क्रमांकन प्रदर्शित करेगा।

```csharp
// रोमन अंकों के साथ पहला शीर्षक बनाएँ
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## चरण 5: दूसरा रोमन अंक शीर्षक जोड़ें

प्रदर्शन के उद्देश्य से, आइए एक दूसरा रोमन अंक शीर्षक जोड़ें, लेकिन इस बार हम 13 से शुरू करेंगे।

स्पष्टीकरण: StartNumber गुण आपको कस्टम संख्या से क्रमांकन शुरू करने की अनुमति देता है - इस मामले में, हम 13 से शुरू कर रहे हैं।

```csharp
// रोमन अंक 13 से शुरू करते हुए दूसरा शीर्षक बनाएं
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## चरण 6: वर्णमाला क्रमांकन के साथ शीर्षक जोड़ें

विविधता के लिए, आइए एक तीसरा शीर्षक जोड़ें, लेकिन इस बार हम छोटे अक्षरों (a, b, c, आदि) में वर्णमाला क्रमांकन का उपयोग करेंगे।

स्पष्टीकरण: NumberingStyle को LettersLowercase में बदलने से हम अपने शीर्षकों पर वर्णानुक्रमिक संख्या लागू कर सकते हैं।

```csharp
// वर्णमाला क्रम में क्रमांकन के साथ शीर्षक बनाएं
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## चरण 7: पीडीएफ को सेव करना

अंत में, सभी शीर्षकों और संख्या शैलियों को लागू करने के बाद, पीडीएफ फाइल को अपनी इच्छित निर्देशिका में सेव करें।

स्पष्टीकरण: यह चरण सभी स्वरूपित शीर्षकों वाली पीडीएफ फाइल को लागू संख्या शैलियों के साथ सहेजता है।

```csharp
// पीडीएफ दस्तावेज़ सहेजें
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## निष्कर्ष

और अब यह हो गया! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में शीर्षकों पर सफलतापूर्वक नंबरिंग शैलियाँ—रोमन अंक और वर्णमाला—लागू की हैं। पेज लेआउट, नंबरिंग शैलियों और सामग्री स्थिति को नियंत्रित करने के लिए Aspose.PDF द्वारा प्रदान की गई लचीलापन आपको सुव्यवस्थित, पेशेवर PDF दस्तावेज़ बनाने के लिए एक शक्तिशाली टूलसेट प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं एक ही PDF दस्तावेज़ पर अलग-अलग संख्या शैलियाँ लागू कर सकता हूँ?  
हां, .NET के लिए Aspose.PDF आपको एक ही दस्तावेज़ में रोमन अंक, अरबी अंक और वर्णमाला क्रमांकन जैसी विभिन्न संख्या शैलियों को मिश्रित करने की अनुमति देता है।

### मैं शीर्षकों के लिए प्रारंभिक संख्या को कैसे अनुकूलित कर सकता हूँ?  
 आप किसी भी शीर्षक के लिए प्रारंभिक संख्या निर्धारित कर सकते हैं`StartNumber` संपत्ति।

### क्या क्रमांकन अनुक्रम को रीसेट करने का कोई तरीका है?  
हां, आप नंबरिंग को समायोजित करके रीसेट कर सकते हैं`StartNumber` प्रत्येक शीर्षक के लिए संपत्ति.

### क्या मैं क्रमांकन के अतिरिक्त शीर्षकों पर बोल्ड या इटैलिक स्टाइलिंग भी लागू कर सकता हूँ?  
 बिल्कुल! आप फ़ॉन्ट, आकार, बोल्ड और इटैलिक जैसे गुणों को संशोधित करके शीर्षक शैलियों को अनुकूलित कर सकते हैं`TextState` वस्तु।

### मैं Aspose.PDF के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?  
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) Aspose.PDF को बिना किसी प्रतिबंध के परीक्षण करने के लिए।