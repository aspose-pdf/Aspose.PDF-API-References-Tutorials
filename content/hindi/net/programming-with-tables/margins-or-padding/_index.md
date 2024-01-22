---
title: मार्जिन या पैडिंग
linktitle: मार्जिन या पैडिंग
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके तालिका में मार्जिन या पैडिंग सेट करना सीखें।
type: docs
weight: 140
url: /hi/net/programming-with-tables/margins-or-padding/
---
इस ट्यूटोरियल में, हम आपको तालिका में मार्जिन या पैडिंग सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग करने की चरण-दर-चरण प्रक्रिया के बारे में मार्गदर्शन करेंगे। हम आपके C# स्रोत कोड में इस कार्यक्षमता को समझने और लागू करने में मदद करने के लिए स्पष्टीकरण और कोड स्निपेट प्रदान करेंगे।

## चरण 1: दस्तावेज़ और पेज सेट करना
आरंभ करने के लिए, आपको निम्नलिखित कोड का उपयोग करके दस्तावेज़ और पेज सेट करना होगा:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ ऑब्जेक्ट को उसके खाली कंस्ट्रक्टर को कॉल करके इंस्टेंट करें
Document doc = new Document();
Page page = doc.Pages.Add();
```

## चरण 2: एक तालिका बनाना
इसके बाद, हम Aspose.Pdf.Table क्लास का उपयोग करके एक टेबल ऑब्जेक्ट बनाएंगे:

```csharp
// किसी तालिका ऑब्जेक्ट को त्वरित करें
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// तालिका को वांछित अनुभाग के पैराग्राफ संग्रह में जोड़ें
page.Paragraphs.Add(tab1);
```

## चरण 3: कॉलम की चौड़ाई और डिफ़ॉल्ट सेल बॉर्डर सेट करना
तालिका की कॉलम चौड़ाई और डिफ़ॉल्ट सेल बॉर्डर सेट करने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
// तालिका की कॉलम चौड़ाई निर्धारित करें
tab1. ColumnWidths = "50 50 50";
// बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## चरण 4: टेबल बॉर्डर और सेल पैडिंग सेट करना
टेबल बॉर्डर और सेल पैडिंग सेट करने के लिए, एक मार्जिनइन्फो ऑब्जेक्ट बनाएं और उसके गुण सेट करें:

```csharp
// एक मार्जिनइन्फो ऑब्जेक्ट बनाएं और उसके बाएँ, नीचे, दाएँ और ऊपर मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// डिफ़ॉल्ट सेल पैडिंग को मार्जिनइन्फो ऑब्जेक्ट पर सेट करें
tab1. DefaultCellPadding = margin;

// किसी अन्य अनुकूलित बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके तालिका बॉर्डर सेट करें
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## चरण 5: पंक्तियाँ और कक्ष जोड़ना
अब, तालिका में पंक्तियाँ और कक्ष जोड़ें। हम एक नई पंक्ति बनाएंगे और उसमें सेल जोड़ेंगे:

```csharp
// तालिका में पंक्तियाँ और फिर पंक्तियों में कक्ष बनाएँ
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## चरण 6: कक्षों में पाठ जोड़ना
किसी सेल में टेक्स्ट जोड़ने के लिए, एक TextFragment ऑब्जेक्ट बनाएं और उसे वांछित सेल में जोड़ें:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## चरण 7: पीडीएफ को सहेजना
पीडीएफ दस्तावेज़ को सहेजने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// पीडीएफ को सेव करें
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके मार्जिन या पैडिंग के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ ऑब्जेक्ट को उसके खाली कंस्ट्रक्टर को कॉल करके प्रारंभ करें
Document doc = new Document();
Page page = doc.Pages.Add();
// किसी तालिका ऑब्जेक्ट को त्वरित करें
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// वांछित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(tab1);
// तालिका की कॉलम चौड़ाई के साथ सेट करें
tab1.ColumnWidths = "50 50 50";
// बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// किसी अन्य अनुकूलित बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके टेबल बॉर्डर सेट करें
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// मार्जिनइन्फो ऑब्जेक्ट बनाएं और उसके बाएँ, नीचे, दाएँ और ऊपर मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// डिफ़ॉल्ट सेल पैडिंग को मार्जिनइन्फो ऑब्जेक्ट पर सेट करें
tab1.DefaultCellPadding = margin;
// तालिका में पंक्तियाँ और फिर पंक्तियों में कक्ष बनाएँ
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add('col3 बड़ी टेक्स्ट स्ट्रिंग के साथ सेल के अंदर रखा जाएगा');
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// पीडीएफ को सेव करें
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके किसी तालिका में मार्जिन या पैडिंग सेट करना सफलतापूर्वक सीख लिया है। यह ज्ञान आपकी दस्तावेज़ स्वरूपण क्षमताओं को बढ़ाने और आपकी तालिकाओं को आकर्षक बनाने में मदद करेगा।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं किसी तालिका में अलग-अलग सेल के लिए अलग-अलग मार्जिन या पैडिंग सेट कर सकता हूं?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके तालिका में अलग-अलग सेल के लिए अलग-अलग मार्जिन या पैडिंग सेट कर सकते हैं। दिए गए उदाहरण में, हम इसका उपयोग करके संपूर्ण तालिका के लिए डिफ़ॉल्ट सेल पैडिंग सेट करते हैं`DefaultCellPadding` संपत्ति। विशिष्ट कोशिकाओं के लिए अलग-अलग पैडिंग सेट करने के लिए, आप इसका उपयोग कर सकते हैं`MarginInfo` प्रत्येक सेल का व्यक्तिगत रूप से मूल्यांकन करें और उनके मार्जिन को संशोधित करें।

#### प्रश्न: मैं तालिका का बॉर्डर रंग या शैली कैसे बदल सकता हूँ?

 उ: तालिका के बॉर्डर रंग या शैली को बदलने के लिए, आप संशोधित कर सकते हैं`Color` और`Width` के गुण`BorderInfo` वस्तु। दिए गए उदाहरण में, हम बॉर्डर का रंग काला और चौड़ाई 1F (एक बिंदु) का उपयोग करके सेट करते हैं`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. आप अपनी आवश्यकताओं के अनुसार रंग और चौड़ाई समायोजित कर सकते हैं।

#### प्रश्न: क्या तालिका में शीर्षलेख या पादलेख जोड़ना संभव है?

उ: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके तालिका में शीर्षलेख या पादलेख जोड़ सकते हैं। शीर्षलेख और पादलेख आम तौर पर अलग-अलग पंक्तियाँ होती हैं जिनमें कॉलम लेबल, तालिका शीर्षक या सारांश डेटा जैसी अतिरिक्त जानकारी होती है। आप अतिरिक्त पंक्तियाँ बना सकते हैं, उन्हें अलग ढंग से स्टाइल कर सकते हैं, और उन्हें तालिका सामग्री के ऊपर या नीचे जोड़ सकते हैं।

#### प्रश्न: मैं टेबल सेल के भीतर टेक्स्ट संरेखण को कैसे समायोजित करूं?

 ए: तालिका सेल के भीतर टेक्स्ट संरेखण को समायोजित करने के लिए, आप इसका उपयोग कर सकते हैं`HorizontalAlignment` और`VerticalAlignment` के गुण`TextFragment` वस्तु। उदाहरण के लिए, टेक्स्ट को क्षैतिज रूप से केंद्र-संरेखित करने के लिए, आप सेट कर सकते हैं`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . इसी तरह आप सेट कर सकते हैं`mytext.VerticalAlignment` ऊर्ध्वाधर संरेखण को नियंत्रित करने के लिए.

#### प्रश्न: क्या मैं तालिका कक्षों में पाठ के स्थान पर छवियाँ जोड़ सकता हूँ?

 उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके तालिका कक्षों में छवियां जोड़ सकते हैं। बनाने के बजाय`TextFragment` ऑब्जेक्ट, आप एक बना सकते हैं`Image` ऑब्जेक्ट, छवि फ़ाइल लोड करें, और इसे का उपयोग करके वांछित सेल में जोड़ें`cell.Paragraphs.Add(image);` तरीका। यह आपको पाठ सामग्री के साथ-साथ तालिका में छवियां सम्मिलित करने की अनुमति देता है।