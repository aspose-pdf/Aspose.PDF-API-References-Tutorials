---
title: तालिका पंक्ति सामग्री के लिए पाठ संरेखण
linktitle: तालिका पंक्ति सामग्री के लिए पाठ संरेखण
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF तालिका में पंक्ति सामग्री को संरेखित करना सीखें।
type: docs
weight: 210
url: /hi/net/programming-with-tables/text-alignment-for-table-row-content/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ की तालिका में एक पंक्ति की सामग्री को संरेखित करने के लिए चरण दर चरण मार्गदर्शन करेंगे। हम दिए गए C# स्रोत कोड को समझाएंगे और आपको दिखाएंगे कि इसे कैसे लागू किया जाए।

## चरण 1: पीडीएफ दस्तावेज़ बनाना
सबसे पहले, हम पीडीएफ दस्तावेज़ बनाएंगे:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## चरण 2: तालिका आरंभीकरण
इसके बाद, हम तालिका प्रारंभ करेंगे:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## चरण 3: टेबल बॉर्डर का रंग सेट करना
हम तालिका सीमा रंग को कॉन्फ़िगर करेंगे:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## चरण 4: तालिका सेल बॉर्डर को कॉन्फ़िगर करना
हम टेबल सेल बॉर्डर को कॉन्फ़िगर करने जा रहे हैं:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## चरण 5: तालिका में 10 पंक्तियाँ जोड़ने के लिए लूप करें
अब हम तालिका में 10 पंक्तियाँ जोड़ने के लिए एक लूप का उपयोग करेंगे:

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
अब दस्तावेज़ पृष्ठ पर तालिका जोड़ें:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## चरण 9: पीडीएफ दस्तावेज़ को सहेजना
अंत में, हम पीडीएफ दस्तावेज़ को सहेजेंगे:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके तालिका पंक्ति सामग्री के लिए पाठ संरेखण के लिए उदाहरण स्रोत कोड

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// पीडीएफ दस्तावेज़ बनाएं
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// तालिका का एक नया उदाहरण प्रारंभ करता है
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// टेबल बॉर्डर का रंग लाइटग्रे के रूप में सेट करें
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// तालिका कक्षों के लिए सीमा निर्धारित करें
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
// इनपुट दस्तावेज़ के पहले पृष्ठ पर तालिका ऑब्जेक्ट जोड़ें
tocPage.Paragraphs.Add(table);
// तालिका ऑब्जेक्ट वाले अद्यतन दस्तावेज़ को सहेजें
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## निष्कर्ष
बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में तालिका में पंक्ति की सामग्री को कैसे संरेखित किया जाए। इस चरण-दर-चरण मार्गदर्शिका ने आपको दिखाया कि दस्तावेज़ कैसे बनाएं, तालिका प्रारंभ करें, सीमा और संरेखण कॉन्फ़िगर करें, सामग्री जोड़ें और पीडीएफ दस्तावेज़ को सहेजें। अब आप इस ज्ञान को अपनी परियोजनाओं पर लागू कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं तालिका कक्षों की सामग्री को क्षैतिज रूप से कैसे संरेखित कर सकता हूं?

 उ: आप सेट करके तालिका कक्षों की सामग्री को क्षैतिज रूप से संरेखित कर सकते हैं`HorizontalAlign` कोशिका की संपत्ति`TextState` वस्तु। उदाहरण के लिए, टेक्स्ट को केंद्र-संरेखित करने के लिए, उपयोग करें`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . आप इसे सेट भी कर सकते हैं`HorizontalAlignment.Left` या`HorizontalAlignment.Right` क्रमशः बाएँ और दाएँ संरेखण के लिए।

#### प्रश्न: क्या मैं तालिका के भीतर अलग-अलग सेल में अलग-अलग बॉर्डर शैलियाँ और रंग लागू कर सकता हूँ?

 उ: हां, आप तालिका के भीतर अलग-अलग सेल पर अलग-अलग बॉर्डर शैलियाँ और रंग लागू कर सकते हैं। किसी विशिष्ट सेल के लिए बॉर्डर को अनुकूलित करने के लिए, सेट करें`cell.Border` एक नए के लिए संपत्ति`BorderInfo`वांछित सेटिंग्स के साथ ऑब्जेक्ट, जैसे बॉर्डर किनारे, चौड़ाई और रंग।

#### प्रश्न: मैं कक्षों के भीतर तालिका सामग्री के ऊर्ध्वाधर संरेखण को कैसे समायोजित कर सकता हूं?

 उ: आप इसे सेट करके कक्षों के भीतर तालिका सामग्री के ऊर्ध्वाधर संरेखण को समायोजित कर सकते हैं`VerticalAlignment` पंक्ति की संपत्ति`VerticalAlignment.Center`, `VerticalAlignment.Top` , या`VerticalAlignment.Bottom`. यह गुण उस पंक्ति में सभी कोशिकाओं के ऊर्ध्वाधर संरेखण को नियंत्रित करता है।

#### प्रश्न: क्या तालिका में गतिशील रूप से अधिक कॉलम या पंक्तियाँ जोड़ना संभव है?

 उ: हाँ, आप इसका उपयोग करके गतिशील रूप से तालिका में अधिक कॉलम और पंक्तियाँ जोड़ सकते हैं`table.Rows.Add()` नई पंक्तियाँ जोड़ने की विधि और`row.Cells.Add()` पंक्तियों में नई कोशिकाएँ जोड़ने की विधि। आप इसे लूप के अंदर या अपनी विशिष्ट आवश्यकताओं के आधार पर कर सकते हैं।

#### प्रश्न: मैं विशिष्ट कोशिकाओं या संपूर्ण तालिका के लिए पृष्ठभूमि रंग कैसे सेट कर सकता हूं?

 उ: विशिष्ट कक्षों या संपूर्ण तालिका के लिए पृष्ठभूमि रंग सेट करने के लिए, इसका उपयोग करें`BackgroundColor` की संपत्ति`Cell` या`Table` वस्तु। उदाहरण के लिए, किसी सेल का पृष्ठभूमि रंग सेट करने के लिए, उपयोग करें`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.