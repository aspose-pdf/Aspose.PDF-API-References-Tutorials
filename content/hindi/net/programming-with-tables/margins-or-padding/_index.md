---
title: मार्जिन या पैडिंग
linktitle: मार्जिन या पैडिंग
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके तालिका में मार्जिन या पैडिंग सेट करना सीखें।
type: docs
weight: 140
url: /hi/net/programming-with-tables/margins-or-padding/
---
इस ट्यूटोरियल में, हम आपको टेबल में मार्जिन या पैडिंग सेट करने के लिए .NET के लिए Aspose.PDF का उपयोग करने की चरण-दर-चरण प्रक्रिया के माध्यम से मार्गदर्शन करेंगे। हम आपके C# स्रोत कोड में इस कार्यक्षमता को समझने और लागू करने में आपकी सहायता करने के लिए स्पष्टीकरण और कोड स्निपेट प्रदान करेंगे।

## चरण 1: दस्तावेज़ और पृष्ठ सेट करना
आरंभ करने के लिए, आपको निम्नलिखित कोड का उपयोग करके दस्तावेज़ और पृष्ठ सेट करना होगा:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// डॉक्यूमेंट ऑब्जेक्ट को उसके खाली कन्स्ट्रक्टर को कॉल करके इंस्टैंसिएट करें
Document doc = new Document();
Page page = doc.Pages.Add();
```

## चरण 2: तालिका बनाना
इसके बाद, हम Aspose.Pdf.Table वर्ग का उपयोग करके एक तालिका ऑब्जेक्ट बनाएंगे:

```csharp
// तालिका ऑब्जेक्ट को इंस्टैंसिएट करें
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// इच्छित अनुभाग के पैराग्राफ़ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(tab1);
```

## चरण 3: कॉलम की चौड़ाई और डिफ़ॉल्ट सेल बॉर्डर सेट करना
तालिका की स्तंभ चौड़ाई और डिफ़ॉल्ट सेल बॉर्डर सेट करने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
// तालिका की स्तंभ चौड़ाई निर्धारित करें
tab1. ColumnWidths = "50 50 50";
// BorderInfo ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## चरण 4: टेबल बॉर्डर और सेल पैडिंग सेट करना
तालिका बॉर्डर और सेल पैडिंग सेट करने के लिए, एक MarginInfo ऑब्जेक्ट बनाएं और उसके गुण सेट करें:

```csharp
// एक मार्जिनइन्फो ऑब्जेक्ट बनाएं और उसके बाएं, निचले, दाएं और ऊपरी मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// डिफ़ॉल्ट सेल पैडिंग को MarginInfo ऑब्जेक्ट पर सेट करें
tab1. DefaultCellPadding = margin;

// किसी अन्य अनुकूलित BorderInfo ऑब्जेक्ट का उपयोग करके तालिका बॉर्डर सेट करें
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## चरण 5: पंक्तियाँ और कक्ष जोड़ना
अब, आइए तालिका में पंक्तियाँ और कक्ष जोड़ें। हम एक नई पंक्ति बनाएंगे और उसमें कक्ष जोड़ेंगे:

```csharp
//तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## चरण 6: कक्षों में पाठ जोड़ना
किसी सेल में टेक्स्ट जोड़ने के लिए, TextFragment ऑब्जेक्ट बनाएं और उसे इच्छित सेल में जोड़ें:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## चरण 7: पीडीएफ को सेव करना
पीडीएफ दस्तावेज़ को सहेजने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// पीडीएफ सहेजें
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके मार्जिन या पैडिंग के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// डॉक्यूमेंट ऑब्जेक्ट को उसके खाली कन्स्ट्रक्टर को कॉल करके इंस्टैंटिएट करें
Document doc = new Document();
Page page = doc.Pages.Add();
// तालिका ऑब्जेक्ट को इंस्टैंसिएट करें
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// इच्छित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(tab1);
// तालिका की स्तंभ चौड़ाई के साथ सेट करें
tab1.ColumnWidths = "50 50 50";
// BorderInfo ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// किसी अन्य अनुकूलित BorderInfo ऑब्जेक्ट का उपयोग करके तालिका बॉर्डर सेट करें
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo ऑब्जेक्ट बनाएं और उसका बायां, निचला, दायां और ऊपरी मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// डिफ़ॉल्ट सेल पैडिंग को MarginInfo ऑब्जेक्ट पर सेट करें
tab1.DefaultCellPadding = margin;
//तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("बड़े टेक्स्ट स्ट्रिंग वाला col3 सेल के अंदर रखा जाना चाहिए");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// पंक्ति1.सेल्स[2].पैराग्राफ[0].फिक्स्डविड्थ= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// पीडीएफ को सुरक्षित रखें
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके तालिका में मार्जिन या पैडिंग कैसे सेट करें। यह ज्ञान आपको अपने दस्तावेज़ स्वरूपण क्षमताओं को बढ़ाने और अपनी तालिकाओं को आकर्षक बनाने में मदद करेगा।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं तालिका में अलग-अलग कक्षों के लिए अलग-अलग मार्जिन या पैडिंग सेट कर सकता हूँ?

 उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके तालिका में अलग-अलग कक्षों के लिए अलग-अलग मार्जिन या पैडिंग सेट कर सकते हैं। दिए गए उदाहरण में, हमने संपूर्ण तालिका के लिए डिफ़ॉल्ट सेल पैडिंग सेट की है।`DefaultCellPadding` प्रॉपर्टी। विशिष्ट कोशिकाओं के लिए अलग-अलग पैडिंग सेट करने के लिए, आप एक्सेस कर सकते हैं`MarginInfo` प्रत्येक कक्ष का अलग-अलग चयन करें और उनके मार्जिन को संशोधित करें।

#### प्रश्न: मैं टेबल का बॉर्डर रंग या शैली कैसे बदल सकता हूँ?

 उत्तर: तालिका के बॉर्डर का रंग या शैली बदलने के लिए, आप संशोधित कर सकते हैं`Color` और`Width` के गुण`BorderInfo` ऑब्जेक्ट। दिए गए उदाहरण में, हमने बॉर्डर का रंग काला और चौड़ाई 1F (एक बिंदु) निर्धारित की है`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`आप अपनी आवश्यकता के अनुसार रंग और चौड़ाई समायोजित कर सकते हैं।

#### प्रश्न: क्या तालिका में शीर्षलेख या पादलेख जोड़ना संभव है?

उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके तालिका में शीर्षलेख या पादलेख जोड़ सकते हैं। शीर्षलेख और पादलेख आम तौर पर अलग-अलग पंक्तियाँ होती हैं जिनमें कॉलम लेबल, तालिका शीर्षक या सारांश डेटा जैसी अतिरिक्त जानकारी होती है। आप अतिरिक्त पंक्तियाँ बना सकते हैं, उन्हें अलग-अलग तरीके से स्टाइल कर सकते हैं और उन्हें तालिका सामग्री के ऊपर या नीचे जोड़ सकते हैं।

#### प्रश्न: मैं तालिका सेल में पाठ संरेखण कैसे समायोजित करूं?

 उत्तर: किसी तालिका कक्ष में पाठ संरेखण समायोजित करने के लिए, आप इसका उपयोग कर सकते हैं`HorizontalAlignment` और`VerticalAlignment` के गुण`TextFragment` ऑब्जेक्ट। उदाहरण के लिए, टेक्स्ट को क्षैतिज रूप से केंद्र-संरेखित करने के लिए, आप सेट कर सकते हैं`mytext.HorizontalAlignment = HorizontalAlignment.Center;` इसी तरह, आप सेट कर सकते हैं`mytext.VerticalAlignment` ऊर्ध्वाधर संरेखण को नियंत्रित करने के लिए.

#### प्रश्न: क्या मैं तालिका कक्षों में पाठ के स्थान पर चित्र जोड़ सकता हूँ?

 उत्तर: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके टेबल सेल में छवियाँ जोड़ सकते हैं।`TextFragment` ऑब्जेक्ट, आप एक बना सकते हैं`Image` ऑब्जेक्ट, छवि फ़ाइल लोड करें, और इसका उपयोग करके वांछित सेल में जोड़ें`cell.Paragraphs.Add(image);`विधि। यह आपको पाठ सामग्री के साथ तालिका में चित्र सम्मिलित करने की अनुमति देता है।