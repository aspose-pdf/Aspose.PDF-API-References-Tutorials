---
title: पीडीएफ फाइल में तालिका के अंदर HTML टैग
linktitle: पीडीएफ फाइल में तालिका के अंदर HTML टैग
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ PDF फ़ाइल में तालिका के अंदर HTML टैग का उपयोग करना सीखें।
type: docs
weight: 100
url: /hi/net/programming-with-tables/html-tags-inside-table/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में तालिका के अंदर HTML टैग का उपयोग कैसे करें। हम C# में सोर्स कोड को चरण दर चरण समझाएंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि पीडीएफ दस्तावेज़ में तालिका में HTML सामग्री कैसे सम्मिलित करें। चलो शुरू करो!

## चरण 1: वातावरण स्थापित करना
सुनिश्चित करें कि आपने अपने C# विकास परिवेश को .NET के लिए Aspose.PDF के साथ कॉन्फ़िगर किया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नामस्थान आयात करें।

## चरण 2: तालिका डेटा बनाना
हम एक डेटाटेबल बनाते हैं जिसमें स्ट्रिंग प्रकार का "डेटा" कॉलम होता है। फिर हम HTML सामग्री का उपयोग करके इस डेटाटेबल में पंक्तियाँ जोड़ते हैं।

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## चरण 3: दस्तावेज़ और तालिका बनाना
हम एक नया पीडीएफ दस्तावेज़ बनाते हैं और इस दस्तावेज़ में एक पेज जोड़ते हैं। इसके बाद, हम टेबल क्लास का एक उदाहरण प्रारंभ करते हैं और टेबल गुण सेट करते हैं।

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## चरण 4: तालिका में डेटा आयात करना
हम "ImportDataTable" विधि का उपयोग करके डेटाटेबल से डेटा को तालिका में आयात करते हैं। हम यह इंगित करने के लिए विधि पैरामीटर निर्दिष्ट करते हैं कि डेटाटेबल की पंक्तियों और स्तंभों की कौन सी श्रेणी आयात की जानी चाहिए।

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## चरण 5: दस्तावेज़ में तालिका जोड़ना
हम तालिका को दस्तावेज़ पृष्ठ पर जोड़ते हैं।

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## चरण 6: दस्तावेज़ सहेजना
हम पीडीएफ दस्तावेज़ को HTML सामग्री वाली तालिका के साथ सहेजते हैं।

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके तालिका के अंदर HTML टैग के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// तालिका का एक नया उदाहरण प्रारंभ करता है
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//तालिका की स्तंभ चौड़ाई निर्धारित करें
tableProvider.ColumnWidths = "400 50 ";
// टेबल बॉर्डर का रंग लाइटग्रे के रूप में सेट करें
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// तालिका कक्षों के लिए बॉर्डर सेट करें
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में तालिका के अंदर HTML टैग का उपयोग कैसे करें। आप C# का उपयोग करके पीडीएफ दस्तावेज़ में तालिका कोशिकाओं में HTML सामग्री सम्मिलित करने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं।

### पीडीएफ फ़ाइल में तालिका के अंदर HTML टैग के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं तालिका कक्षों के अंदर अन्य HTML टैग और विशेषताओं का उपयोग कर सकता हूँ?

 उ: हाँ, आप तालिका कक्षों के अंदर विभिन्न HTML टैग और विशेषताओं का उपयोग कर सकते हैं, जैसे`<b>`, `<i>`, `<a>`और भी कई। .NET के लिए Aspose.PDF HTML तत्वों और शैलियों की एक विस्तृत श्रृंखला का समर्थन करता है जिनका उपयोग आप तालिका कक्षों के भीतर सामग्री को प्रारूपित करने के लिए कर सकते हैं।

#### प्रश्न: क्या मैं तालिका कक्षों के अंदर HTML सामग्री पर CSS शैलियाँ लागू कर सकता हूँ?

उ: हाँ, आप तालिका कक्षों के अंदर HTML सामग्री पर CSS शैलियाँ लागू कर सकते हैं। .NET के लिए Aspose.PDF बुनियादी CSS शैलियों के लिए समर्थन प्रदान करता है जिन्हें HTML तत्वों पर लागू किया जा सकता है।

#### प्रश्न: क्या तालिका कक्षों के अंदर HTML सामग्री के साथ छवियां जोड़ना संभव है?

 उ: हां, आप तालिका कक्षों के अंदर HTML सामग्री के साथ छवियां जोड़ सकते हैं। आप HTML का उपयोग कर सकते हैं`<img>` स्थानीय फ़ाइलों या यूआरएल जैसे विभिन्न स्रोतों से छवियों को शामिल करने के लिए टैग।

#### प्रश्न: मैं तालिका के लिए अलग-अलग कॉलम चौड़ाई कैसे निर्दिष्ट कर सकता हूं?

 ए: आप इसका उपयोग करके तालिका के लिए अलग-अलग कॉलम चौड़ाई निर्दिष्ट कर सकते हैं`ColumnWidths` तालिका की संपत्ति. प्रॉपर्टी स्पेस-पृथक मानों वाली एक स्ट्रिंग लेती है, जहां प्रत्येक मान बिंदुओं में कॉलम की चौड़ाई का प्रतिनिधित्व करता है।

#### प्रश्न: क्या मैं HTML सामग्री वाले सेल के अंदर नेस्टेड तालिकाओं का उपयोग कर सकता हूँ?

उ: हाँ, आप HTML सामग्री वाले सेल के अंदर नेस्टेड तालिकाओं का उपयोग कर सकते हैं। आप अलग-अलग तालिका उदाहरण बना सकते हैं और नेस्टिंग प्रभाव प्राप्त करने के लिए उन्हें सेल के अंदर HTML सामग्री के हिस्से के रूप में जोड़ सकते हैं।