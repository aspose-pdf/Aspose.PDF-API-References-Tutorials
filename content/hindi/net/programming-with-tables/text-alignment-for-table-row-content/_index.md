---
title: तालिका पंक्ति सामग्री के लिए पाठ संरेखण
linktitle: तालिका पंक्ति सामग्री के लिए पाठ संरेखण
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF तालिका में पंक्ति सामग्री को संरेखित करना सीखें।
type: docs
weight: 210
url: /hi/net/programming-with-tables/text-alignment-for-table-row-content/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ की तालिका में पंक्ति की सामग्री को संरेखित करने के लिए चरण दर चरण मार्गदर्शन करेंगे। हम प्रदान किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको दिखाएंगे कि इसे कैसे लागू किया जाए।

## चरण 1: पीडीएफ दस्तावेज़ बनाना
सबसे पहले, हम PDF दस्तावेज़ बनाएंगे:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## चरण 2: तालिका आरंभीकरण
इसके बाद, हम तालिका को आरंभ करेंगे:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## चरण 3: टेबल बॉर्डर का रंग सेट करना
हम तालिका बॉर्डर का रंग कॉन्फ़िगर करेंगे:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## चरण 4: तालिका सेल बॉर्डर को कॉन्फ़िगर करना
हम तालिका सेल बॉर्डर को कॉन्फ़िगर करने जा रहे हैं:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## चरण 5: तालिका में 10 पंक्तियाँ जोड़ने के लिए लूप करें
अब हम तालिका में 10 पंक्तियाँ जोड़ने के लिए लूप का उपयोग करेंगे:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## चरण 6: ऊर्ध्वाधर रेखा संरेखण को कॉन्फ़िगर करना
हम तालिका की पंक्तियों के ऊर्ध्वाधर संरेखण को कॉन्फ़िगर करने जा रहे हैं:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## चरण 7: पंक्ति कक्षों में सामग्री जोड़ना
हम पंक्ति कक्षों में सामग्री जोड़ने जा रहे हैं:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## चरण 8: दस्तावेज़ पृष्ठ पर तालिका जोड़ना
अब आइए दस्तावेज़ पृष्ठ में तालिका जोड़ें:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## चरण 9: पीडीएफ दस्तावेज़ को सहेजना
अंत में, हम पीडीएफ दस्तावेज़ को सेव करेंगे:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके तालिका पंक्ति सामग्री के लिए पाठ संरेखण के लिए उदाहरण स्रोत कोड

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// पीडीएफ दस्तावेज़ बनाएं
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// तालिका का एक नया उदाहरण आरंभ करता है
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// टेबल बॉर्डर का रंग हल्का ग्रे पर सेट करें
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// तालिका कक्षों के लिए बॉर्डर सेट करें
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 10 पंक्तियाँ जोड़ने के लिए एक लूप बनाएँ
for (int row_count = 0; row_count < 10; row_count++)
{
	// तालिका में पंक्ति जोड़ें
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// इनपुट दस्तावेज़ के प्रथम पृष्ठ पर तालिका ऑब्जेक्ट जोड़ें
tocPage.Paragraphs.Add(table);
// तालिका ऑब्जेक्ट युक्त अद्यतन दस्तावेज़ सहेजें
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## निष्कर्ष
बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में तालिका में पंक्ति की सामग्री को कैसे संरेखित किया जाए। इस चरण-दर-चरण मार्गदर्शिका ने आपको दिखाया कि दस्तावेज़ कैसे बनाएँ, तालिका आरंभ करें, बॉर्डर और संरेखण कॉन्फ़िगर करें, सामग्री जोड़ें और PDF दस्तावेज़ को कैसे सहेजें। अब आप इस ज्ञान को अपनी खुद की परियोजनाओं पर लागू कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं तालिका कक्षों की सामग्री को क्षैतिज रूप से कैसे संरेखित कर सकता हूं?

 उत्तर: आप तालिका कक्षों की सामग्री को क्षैतिज रूप से सेट करके संरेखित कर सकते हैं`HorizontalAlign` कोशिका की संपत्ति`TextState` ऑब्जेक्ट। उदाहरण के लिए, टेक्स्ट को केंद्र में संरेखित करने के लिए, उपयोग करें`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . आप इसे इस पर भी सेट कर सकते हैं`HorizontalAlignment.Left` या`HorizontalAlignment.Right` क्रमशः बाएं और दाएं संरेखण के लिए।

#### प्रश्न: क्या मैं तालिका के भीतर अलग-अलग कक्षों पर अलग-अलग बॉर्डर शैलियाँ और रंग लागू कर सकता हूँ?

 उत्तर: हां, आप टेबल के अंदर अलग-अलग सेल पर अलग-अलग बॉर्डर स्टाइल और रंग लागू कर सकते हैं। किसी खास सेल के लिए बॉर्डर कस्टमाइज़ करने के लिए, सेट करें`cell.Border` संपत्ति को एक नए रूप में`BorderInfo`ऑब्जेक्ट को वांछित सेटिंग्स के साथ सेट करें, जैसे बॉर्डर साइड, चौड़ाई और रंग।

#### प्रश्न: मैं कक्षों के भीतर तालिका सामग्री के ऊर्ध्वाधर संरेखण को कैसे समायोजित कर सकता हूं?

 उत्तर: आप कक्षों के भीतर तालिका सामग्री के ऊर्ध्वाधर संरेखण को सेट करके समायोजित कर सकते हैं`VerticalAlignment` पंक्ति की संपत्ति`VerticalAlignment.Center`, `VerticalAlignment.Top` , या`VerticalAlignment.Bottom`यह गुण उस पंक्ति में सभी कक्षों के ऊर्ध्वाधर संरेखण को नियंत्रित करता है।

#### प्रश्न: क्या तालिका में गतिशील रूप से अधिक कॉलम या पंक्तियाँ जोड़ना संभव है?

 उत्तर: हां, आप गतिशील रूप से तालिका में अधिक कॉलम और पंक्तियां जोड़ सकते हैं`table.Rows.Add()` नई पंक्तियाँ जोड़ने की विधि और`row.Cells.Add()` पंक्तियों में नए सेल जोड़ने की विधि। आप इसे लूप के अंदर या अपनी विशिष्ट आवश्यकताओं के आधार पर कर सकते हैं।

#### प्रश्न: मैं विशिष्ट कक्षों या संपूर्ण तालिका के लिए पृष्ठभूमि रंग कैसे सेट कर सकता हूं?

 उत्तर: विशिष्ट कक्षों या संपूर्ण तालिका के लिए पृष्ठभूमि रंग सेट करने के लिए, का उपयोग करें`BackgroundColor` की संपत्ति`Cell` या`Table` ऑब्जेक्ट. उदाहरण के लिए, किसी सेल का बैकग्राउंड रंग सेट करने के लिए, उपयोग करें`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.