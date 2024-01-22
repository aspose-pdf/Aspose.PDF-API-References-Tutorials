---
title: पीडीएफ दस्तावेज़ में तालिका प्रस्तुत करें
linktitle: पीडीएफ दस्तावेज़ में तालिका प्रस्तुत करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में तालिका प्रदर्शित करना सीखें।
type: docs
weight: 170
url: /hi/net/programming-with-tables/render-table/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में एक तालिका प्रदर्शित करने के लिए चरण दर चरण मार्गदर्शन करेंगे। हम दिए गए C# स्रोत कोड को समझाएंगे और आपको दिखाएंगे कि इसे कैसे लागू किया जाए।

## चरण 1: दस्तावेज़ बनाना
सबसे पहले, हम एक नया पीडीएफ दस्तावेज़ बनाएंगे:

```csharp
// दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();
```

## चरण 2: पेज मार्जिन और ओरिएंटेशन को कॉन्फ़िगर करना
इसके बाद, हम पेज मार्जिन को कॉन्फ़िगर करेंगे और ओरिएंटेशन को लैंडस्केप मोड पर सेट करेंगे:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## चरण 3: तालिका और कॉलम बनाना
अब एक तालिका बनाएं और कॉलम की चौड़ाई निर्धारित करें:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## चरण 4: तालिका में पंक्तियाँ और कक्ष जोड़ें
इसके बाद, हम एक लूप का उपयोग करके तालिका में पंक्तियाँ और सेल जोड़ेंगे:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## चरण 5: तालिका को पृष्ठ पर जोड़ना
अब दस्तावेज़ पृष्ठ पर तालिका जोड़ें:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## चरण 6: तालिका को एक नए पृष्ठ पर प्रदर्शित करना
इसके बाद, हम एक नई तालिका बनाएंगे और तालिका को एक नए पृष्ठ पर प्रदर्शित करने के लिए "IsInNewPage" प्रॉपर्टी को "सही" पर सेट करेंगे:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## चरण 7: पीडीएफ सहेजें
अंत में, हम पीडीएफ दस्तावेज़ को सहेजते हैं:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके रेंडर टेबल के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// पेज जोड़ा गया.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// कृपया मैं तालिका 1 को अगले पृष्ठ पर रखना चाहता हूँ...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## निष्कर्ष
बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में तालिका कैसे प्रदर्शित करें। इस चरण-दर-चरण मार्गदर्शिका ने आपको दिखाया कि दस्तावेज़ कैसे बनाएं, पेज मार्जिन और ओरिएंटेशन को कॉन्फ़िगर करें, एक तालिका जोड़ें और एक नए पृष्ठ पर एक तालिका प्रदर्शित करें। अब आप इस ज्ञान को अपनी परियोजनाओं पर लागू कर सकते हैं।

### पीडीएफ दस्तावेज़ में तालिका प्रस्तुत करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं तालिका के स्वरूप को कैसे संशोधित कर सकता हूं, जैसे सेल रंग बदलना या बॉर्डर जोड़ना?

उ: तालिका के स्वरूप को संशोधित करने के लिए, आप इसके विभिन्न गुण सेट कर सकते हैं`Aspose.Pdf.Table` और इसकी कोशिकाएँ। उदाहरण के लिए, आप सेट कर सकते हैं`BackgroundColor` कोशिकाओं की पृष्ठभूमि का रंग बदलने का गुण। आप भी सेट कर सकते हैं`Border` बॉर्डर जोड़ने के लिए तालिका या व्यक्तिगत कक्षों की संपत्ति। इसके अतिरिक्त, आप फ़ॉन्ट, टेक्स्ट रंग और तालिका सामग्री के संरेखण को संशोधित करके अनुकूलित कर सकते हैं`TextState` की`TextFragment` वस्तुओं को कोशिकाओं में जोड़ा गया।

#### प्रश्न: क्या मैं तालिका में शीर्षलेख या पादलेख जोड़ सकता हूँ?

उ: हाँ, आप तालिका के आरंभ या अंत में अतिरिक्त पंक्तियाँ बनाकर और कक्षों में उपयुक्त सामग्री सेट करके तालिका में शीर्षलेख या पादलेख जोड़ सकते हैं। आप इन विशिष्ट पंक्तियों में विभिन्न शैलियाँ या सामग्री जोड़कर शीर्ष लेख या पाद लेख को शेष तालिका सामग्री से स्वतंत्र रूप से अनुकूलित कर सकते हैं।

#### प्रश्न: मैं पृष्ठ पर तालिका की स्थिति को कैसे नियंत्रित कर सकता हूं?

 उ: पृष्ठ पर तालिका की स्थिति को नियंत्रित करने के लिए, आप इसे समायोजित कर सकते हैं`MarginInfo` की`PageInfo` वस्तु।`MarginInfo`आपको पृष्ठ के बाएँ, दाएँ, ऊपर और नीचे मार्जिन सेट करने की अनुमति देता है, जो तालिका के लिए उपलब्ध स्थान को प्रभावित करता है। आप भी उपयोग कर सकते हैं`PositioningType` की संपत्ति`Aspose.Pdf.Table` पृष्ठ के सामग्री क्षेत्र के भीतर इसके क्षैतिज और ऊर्ध्वाधर संरेखण को नियंत्रित करने के लिए।

#### प्रश्न: क्या मैं तालिका को एक्सेल या सीएसवी जैसे विभिन्न फ़ाइल स्वरूपों में निर्यात कर सकता हूँ?

उत्तर: .NET के लिए Aspose.PDF मुख्य रूप से PDF दस्तावेज़ों के साथ काम करने के लिए डिज़ाइन किया गया है। हालाँकि यह पीडीएफ दस्तावेज़ को एक छवि या एक्सपीएस के रूप में निर्यात कर सकता है, लेकिन यह एक्सेल या सीएसवी जैसे प्रारूपों में तालिकाओं को निर्यात करने का सीधे समर्थन नहीं करता है। तालिका डेटा को विभिन्न फ़ाइल स्वरूपों में निर्यात करने के लिए, आपको पीडीएफ सामग्री को वांछित प्रारूप में परिवर्तित करने के लिए अतिरिक्त पुस्तकालयों या विधियों का उपयोग करने की आवश्यकता हो सकती है।

#### प्रश्न: मैं तालिका कक्षों में हाइपरलिंक कैसे जोड़ सकता हूं?

 उ: तालिका कक्षों में हाइपरलिंक जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`Aspose.Pdf.WebHyperlink` हाइपरलिंक बनाने के लिए क्लास का उपयोग करें और फिर इसे एंकर के रूप में जोड़ें`TextFragment`कोशिका के अंदर. यह आपको सेल के भीतर विशिष्ट पाठ या सामग्री के साथ एक यूआरएल या लिंक लक्ष्य को जोड़ने, क्लिक करने योग्य हाइपरलिंक बनाने की अनुमति देता है।