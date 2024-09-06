---
title: पीडीएफ फाइल में छवि के चारों ओर पाठ रखना
linktitle: पीडीएफ फाइल में छवि के चारों ओर पाठ रखना
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छवि के चारों ओर पाठ रखना सीखें।
type: docs
weight: 260
url: /hi/net/programming-with-text/placing-text-around-image/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF फ़ाइल में किसी छवि के चारों ओर टेक्स्ट कैसे रखें। हम दिए गए C# स्रोत कोड का उपयोग करके तालिका बनाने, छवि जोड़ने और छवि के चारों ओर टेक्स्ट की स्थिति निर्धारित करने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आप जेनरेट की गई पीडीएफ फाइल को सेव करना चाहते हैं।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपने इच्छित निर्देशिका के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ और पृष्ठ बनाएँ

 इसके बाद, हम एक बनाते हैं`Document` ऑब्जेक्ट और इसका उपयोग करके इसमें एक पेज जोड़ें`Pages.Add()` तरीका।

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## चरण 3: एक तालिका बनाएं

 हम इसका उपयोग करके एक तालिका बनाते हैं`Table` क्लास चुनें और उसे पृष्ठ के पैराग्राफ़ संग्रह में जोड़ें।

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## चरण 4: तालिका कॉलम की चौड़ाई और मार्जिन सेट करें

 हम तालिका के कॉलम की चौड़ाई निर्धारित करते हैं और एक बनाते हैं`MarginInfo` मार्जिन सेट करने के लिए ऑब्जेक्ट का उपयोग करें.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## चरण 5: तालिका में एक छवि जोड़ें

 हम एक बनाते हैं`Image` ऑब्जेक्ट, छवि फ़ाइल पथ निर्दिष्ट करें, और छवि की निश्चित ऊंचाई और चौड़ाई सेट करें। फिर, हम छवि को टेबल सेल के पैराग्राफ संग्रह में जोड़ते हैं।

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## चरण 6: छवि के चारों ओर पाठ जोड़ें

 हम HTML-स्वरूपित पाठ युक्त स्ट्रिंग वैरिएबल बनाते हैं और एक बनाते हैं`HtmlFragment`फिर, हम छवि वाले टेबल सेल में HTML टेक्स्ट जोड़ते हैं।

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## चरण 7: अतिरिक्त पाठ जोड़ें

 हम एक और बनाते हैं`HtmlFragment` अतिरिक्त HTML-स्वरूपित पाठ युक्त ऑब्जेक्ट को एक अलग तालिका कक्ष में जोड़ें।

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## चरण 8: पीडीएफ दस्तावेज़ सहेजें

अंत में, हम पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके छवि के चारों ओर पाठ रखने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ ऑब्जेक्ट को इंस्टैंसिएट करें
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// पीडीएफ में एक पेज बनाएं
Aspose.Pdf.Page page = doc.Pages.Add();
// तालिका ऑब्जेक्ट को इंस्टैंसिएट करें
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// इच्छित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table1);
// तालिका की स्तंभ चौड़ाई के साथ सेट करें
table1.ColumnWidths = "120 270";
// MarginInfo ऑब्जेक्ट बनाएं और उसका बायां, निचला, दायां और ऊपरी मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// डिफ़ॉल्ट सेल पैडिंग को MarginInfo ऑब्जेक्ट पर सेट करें
table1.DefaultCellPadding = margin;
// तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
Aspose.Pdf.Row row1 = table1.Rows.Add();
// एक छवि ऑब्जेक्ट बनाएँ
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// छवि फ़ाइल पथ निर्दिष्ट करें
logo.File = dataDir + "aspose-logo.jpg";
// छवि की निश्चित ऊंचाई निर्दिष्ट करें
logo.FixHeight = 120;
// छवि की निश्चित चौड़ाई निर्दिष्ट करें
logo.FixWidth = 110;
row1.Cells.Add();
// तालिका सेल के पैराग्राफ़ संग्रह में छवि जोड़ें
row1.Cells[0].Paragraphs.Add(logo);
// HTML टैग वाले टेक्स्ट के साथ स्ट्रिंग वैरिएबल बनाएं
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//छवि के दाईं ओर जोड़ने के लिए एक टेक्स्ट ऑब्जेक्ट बनाएं
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// HTML टेक्स्ट वाले पैराग्राफ़ को टेबल सेल में जोड़ें
row1.Cells[1].Paragraphs.Add(TitleText);
// पंक्ति सामग्री का ऊर्ध्वाधर संरेखण शीर्ष के रूप में सेट करें
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// दूसरी पंक्ति के लिए पंक्ति अवधि मान 2 के रूप में सेट करें
SecondRow.Cells[0].ColSpan = 2;
// दूसरी पंक्ति के ऊर्ध्वाधर संरेखण को शीर्ष के रूप में सेट करें
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// HTML टेक्स्ट वाले पैराग्राफ़ को टेबल सेल में जोड़ें
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// पीडीएफ फाइल को सेव करें
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में किसी छवि के चारों ओर टेक्स्ट कैसे रखें। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक टेबल बना सकते हैं, एक छवि जोड़ सकते हैं, और PDF दस्तावेज़ में छवि के चारों ओर टेक्स्ट रख सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में छवि के चारों ओर टेक्स्ट रखना" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में इमेज के चारों ओर टेक्स्ट रखना" ट्यूटोरियल दर्शाता है कि पीडीएफ दस्तावेज़ में इमेज के चारों ओर टेक्स्ट रखने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल आपको टेबल बनाने, इमेज जोड़ने और इमेज के चारों ओर टेक्स्ट रखने में मदद करने के लिए चरण-दर-चरण गाइड और C# स्रोत कोड प्रदान करता है।

#### प्रश्न: मैं PDF दस्तावेज़ में छवि के चारों ओर पाठ क्यों रखना चाहूंगा?

उत्तर: किसी छवि के चारों ओर पाठ रखने से आपके PDF दस्तावेज़ों की दृश्य प्रस्तुति बेहतर हो जाती है, जिससे वे अधिक आकर्षक और जानकारीपूर्ण बन जाते हैं। इस तकनीक का उपयोग अक्सर दस्तावेज़ों, ब्रोशर, रिपोर्ट और अन्य सामग्रियों में किया जाता है जहाँ आप छवियों और पाठ को सौंदर्यपूर्ण रूप से आकर्षक तरीके से जोड़ना चाहते हैं।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे स्थापित करूँ?

उत्तर: दस्तावेज़ निर्देशिका सेट अप करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका का पथ वाला वेरिएबल जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं।

#### प्रश्न: मैं तालिका कैसे बनाऊं और उसमें छवि कैसे जोड़ूं?

 उत्तर: यह ट्यूटोरियल आपको तालिका बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करता है`Table` क्लास का उपयोग करके तालिका में एक छवि जोड़ना`Image` क्लास। आप किसी तालिका सेल में जोड़ने से पहले छवि फ़ाइल पथ, ऊंचाई और चौड़ाई निर्दिष्ट करेंगे।

#### प्रश्न: मैं छवि के चारों ओर पाठ कैसे रखूं?

 उत्तर: छवि के चारों ओर पाठ की स्थिति निर्धारित करने के लिए, आप HTML-स्वरूपित पाठ का निर्माण करेंगे।`HtmlFragment` क्लास। इस टेक्स्ट में शीर्षक और बॉडी टेक्स्ट दोनों होंगे। फिर आप इस HTML टेक्स्ट को टेबल सेल में जोड़ेंगे जो इमेज सेल के बगल में है।

#### प्रश्न: क्या मैं पाठ और छवि के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हाँ, आप HTML टैग और प्रॉपर्टी का उपयोग करके टेक्स्ट और इमेज के स्वरूप को अनुकूलित कर सकते हैं। उदाहरण के लिए, आप टेक्स्ट के लिए फ़ॉन्ट आकार, रंग, शैली और संरेखण सेट कर सकते हैं। इसके अतिरिक्त, आप इमेज के आकार और आयाम को समायोजित कर सकते हैं।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ कैसे सहेजूं?

 उत्तर: तालिका में छवि और पाठ जोड़ने के बाद, आप पीडीएफ दस्तावेज़ को सहेज सकते हैं`Save` की विधि`Document` वर्ग। वांछित आउटपुट फ़ाइल पथ को तर्क के रूप में प्रदान करें`Save` तरीका।

#### प्रश्न: इस ट्यूटोरियल का अपेक्षित आउटपुट क्या है?

उत्तर: ट्यूटोरियल का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक PDF दस्तावेज़ तैयार करेंगे जो दर्शाता है कि किसी छवि के चारों ओर टेक्स्ट कैसे रखा जाए। आउटपुट दस्तावेज़ में एक टेबल होगी जिसमें एक छवि और उसके चारों ओर टेक्स्ट रखा होगा।

#### प्रश्न: क्या मैं JPG के अलावा अन्य छवि प्रारूपों का उपयोग कर सकता हूँ?

 उत्तर: हां, आप Aspose.PDF लाइब्रेरी द्वारा समर्थित विभिन्न छवि प्रारूपों का उपयोग कर सकते हैं, जैसे PNG, BMP, GIF, और अधिक। बनाते समय`Image` ऑब्जेक्ट में, इच्छित छवि प्रारूप का फ़ाइल पथ निर्दिष्ट करें.

#### प्रश्न: क्या इस ट्यूटोरियल के लिए वैध एस्पोज लाइसेंस आवश्यक है?

उत्तर: हां, इस ट्यूटोरियल को सही तरीके से काम करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से एक पूर्ण लाइसेंस खरीद सकते हैं या 30-दिन का अस्थायी लाइसेंस प्राप्त कर सकते हैं।