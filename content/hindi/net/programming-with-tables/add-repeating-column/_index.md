---
title: पीडीएफ दस्तावेज़ में दोहराव वाला कॉलम जोड़ें
linktitle: पीडीएफ दस्तावेज़ में दोहराव वाला कॉलम जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में दोहराव वाला कॉलम जोड़ने का तरीका जानें।
type: docs
weight: 20
url: /hi/net/programming-with-tables/add-repeating-column/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में एक दोहराव वाला कॉलम कैसे जोड़ा जाए। हम C# में सोर्स कोड को चरण दर चरण समझाएंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि पीडीएफ दस्तावेज़ में दोहराए जाने वाले कॉलम के साथ तालिका कैसे बनाई जाती है। चलो शुरू करो!

## चरण 1: वातावरण स्थापित करना
सबसे पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF के साथ अपना C# विकास वातावरण स्थापित कर लिया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नामस्थान आयात करें।

## चरण 2: पीडीएफ दस्तावेज़ बनाना
इस चरण में, हम एक नया पीडीएफ दस्तावेज़ बनाते हैं।

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

हमने एक खाली पीडीएफ दस्तावेज़ बनाया है जहां हम सामग्री जोड़ सकते हैं।

## चरण 3: तालिकाएँ बनाना
इस चरण में हम एक मुख्य तालिका बनाते हैं (`outerTable`) और एक नेस्टेड टेबल (`mytable`) जिसे कॉलम में दोहराया जाएगा।

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

हमने कॉलम की चौड़ाई और नेस्टेड टेबल ब्रेक मोड जैसी तालिका गुण निर्दिष्ट किए हैं।

## चरण 4: दस्तावेज़ में तालिकाएँ जोड़ना
अब हम बनाई गई तालिकाओं को पीडीएफ दस्तावेज़ में जोड़ते हैं।

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

हम पहले मुख्य तालिका जोड़ते हैं (`outerTable`) पीडीएफ दस्तावेज़ में। इसके बाद, हम नेस्टेड टेबल जोड़ते हैं (`mytable` ) मुख्य तालिका में एक सेल में एक पैराग्राफ के रूप में। हम इसके लिए दोहराए गए स्तंभों की संख्या भी निर्दिष्ट करते हैं`mytable` (इस उदाहरण में, 5 कॉलम)।

## चरण 5: शीर्षलेख और पंक्तियाँ जोड़ना
अब हम तालिका में शीर्षलेख और पंक्तियाँ जोड़ते हैं।

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// यहां अन्य शीर्षलेख जोड़ें

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // अन्य कॉलम यहां जोड़ें
}
```

हम सबसे पहले हेडर को तालिका की पहली पंक्ति में जोड़ते हैं (`headerRow`). फिर हम एक लूप से डेटा की पंक्तियाँ जोड़ते हैं। इस उदाहरण में, हम डेटा की 6 पंक्तियाँ जोड़ते हैं।

## चरण 6: पीडीएफ दस्तावेज़ को सहेजना
अंत में, हम पीडीएफ दस्तावेज़ को निर्दिष्ट फ़ाइल में सहेजते हैं।

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

आउटपुट पीडीएफ फ़ाइल को सहेजने के लिए सही निर्देशिका और फ़ाइल नाम निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.PDF का उपयोग करके दोहराए जाने वाले कॉलम को जोड़ने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// एक बाहरी तालिका को इंस्टेंट करें जो पूरे पृष्ठ को ले ले
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//एक टेबल ऑब्जेक्ट को इंस्टेंटियेट करें जिसे आउटरटेबल के अंदर नेस्ट किया जाएगा जो उसी पेज के अंदर टूट जाएगा
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// पृष्ठ पैराग्राफ में बाहरी तालिका जोड़ें
// मायटेबल को आउटरटेबल में जोड़ें
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// हेडर पंक्ति जोड़ें
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// तालिका में पंक्तियाँ और फिर पंक्तियों में कक्ष बनाएँ
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में एक दोहराव वाला कॉलम कैसे जोड़ा जाए। आप अपने स्वयं के C# प्रोजेक्ट में दोहराए जाने वाले कॉलम वाली तालिकाएँ बनाने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं।

### पीडीएफ दस्तावेज़ में दोहराव वाला कॉलम जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं नेस्टेड तालिका में दोहराए गए स्तंभों की संख्या को अनुकूलित कर सकता हूँ?

 उत्तर: हाँ, आप नेस्टेड तालिका में दोहराए गए कॉलमों की संख्या को अनुकूलित कर सकते हैं। दिए गए उदाहरण में, हमने सेट किया है`mytable.RepeatingColumnsCount = 5;`, जिसका अर्थ है कि 5 दोहराए गए कॉलम होंगे। आप इस मान को किसी भी वांछित संख्या में बदल सकते हैं।

#### प्रश्न: क्या नेस्टेड तालिका में गतिशील रूप से अधिक पंक्तियाँ जोड़ना संभव है?

उ: हाँ, आप नेस्टेड तालिका में गतिशील रूप से उसी तरह अधिक पंक्तियाँ जोड़ सकते हैं जैसे ट्यूटोरियल में दिखाया गया है। आप अपने डेटा के आधार पर पंक्तियाँ जोड़ने के लिए लूप या किसी अन्य तर्क का उपयोग कर सकते हैं।

#### प्रश्न: क्या मैं तालिका और उसके कक्षों में शैलियाँ और फ़ॉर्मेटिंग लागू कर सकता हूँ?

उ: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके तालिका और उसके कक्षों में शैलियाँ और फ़ॉर्मेटिंग लागू कर सकते हैं। लाइब्रेरी तालिका और उसकी सामग्री के स्वरूप को अनुकूलित करने के लिए विभिन्न गुण और विधियाँ प्रदान करती है।

#### प्रश्न: क्या .NET के लिए Aspose.PDF .NET कोर के साथ संगत है?

उत्तर: हां, .NET के लिए Aspose.PDF .NET कोर के साथ संगत है। आप इसे .NET फ्रेमवर्क और .NET कोर एप्लिकेशन दोनों में उपयोग कर सकते हैं।

#### प्रश्न: क्या मैं मौजूदा पीडीएफ दस्तावेज़ में दोहराए जाने वाले कॉलम जोड़ने के लिए इस दृष्टिकोण का उपयोग कर सकता हूं?

उ: हां, आप मौजूदा पीडीएफ दस्तावेज़ में दोहराए जाने वाले कॉलम जोड़ने के लिए इस दृष्टिकोण का उपयोग कर सकते हैं। बस .NET के लिए Aspose.PDF का उपयोग करके मौजूदा दस्तावेज़ को लोड करें और दोहराए जाने वाले कॉलम को बनाने और जोड़ने के लिए समान चरणों का पालन करें।