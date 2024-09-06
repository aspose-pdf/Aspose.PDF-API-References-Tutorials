---
title: पीडीएफ फाइल में पेज ब्रेक डालें
linktitle: पीडीएफ फाइल में पेज ब्रेक डालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पृष्ठ विराम सम्मिलित करना सीखें।
type: docs
weight: 110
url: /hi/net/programming-with-tables/insert-page-break/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पेज ब्रेक कैसे डालें। हम C# में सोर्स कोड को चरण दर चरण समझाएँगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि PDF दस्तावेज़ की तालिका में एक निश्चित संख्या में पंक्तियों के बाद पेज ब्रेक कैसे जोड़ा जाता है। चलिए शुरू करते हैं!

## चरण 1: वातावरण की स्थापना
सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF के साथ अपना C# डेवलपमेंट एनवायरनमेंट कॉन्फ़िगर किया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नेमस्पेस आयात करें।

## चरण 2: दस्तावेज़ और तालिका बनाना
हम एक नया डॉक्यूमेंट इंस्टेंस बनाते हैं और इस डॉक्यूमेंट में एक पेज जोड़ते हैं। इसके बाद, हम PDF डॉक्यूमेंट में अपनी टेबल को दर्शाने के लिए एक टेबल इंस्टेंस बनाते हैं। हम टेबल के लिए बॉर्डर स्टाइल भी परिभाषित करते हैं।

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## चरण 3: तालिका में पंक्तियाँ जोड़ें
हम सरणी में 200 पंक्तियाँ जोड़ने के लिए लूप का उपयोग करते हैं। प्रत्येक पंक्ति के लिए, हम Row का एक उदाहरण बनाते हैं और टेक्स्ट सामग्री के साथ दो सेल जोड़ते हैं।

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // जब 10 पंक्तियाँ जोड़ी जाती हैं, तो हम एक नया पृष्ठ विराम सम्मिलित करते हैं
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## चरण 4: दस्तावेज़ में तालिका जोड़ना
हम दस्तावेज़ पृष्ठ के पैराग्राफ़ संग्रह में तालिका जोड़ते हैं।

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## चरण 5: दस्तावेज़ सहेजें
हम पीडीएफ दस्तावेज़ को पृष्ठ विराम सहित सहेजते हैं।

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके पेज ब्रेक सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ उदाहरण को तत्कालित करें
Document doc = new Document();
// पीडीएफ फाइल के पेज टू पेज संग्रह को जोड़ें
doc.Pages.Add();
// तालिका उदाहरण बनाएँ
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// तालिका के लिए बॉर्डर शैली सेट करें
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// लाल बॉर्डर रंग वाली तालिका के लिए डिफ़ॉल्ट बॉर्डर शैली सेट करें
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// तालिका कॉलम की चौड़ाई निर्दिष्ट करें
tab.ColumnWidths = "100 100";
// तालिका में 200 पंक्तियाँ जोड़ने के लिए लूप बनाएँ
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// जब 10 पंक्तियाँ जोड़ी जाती हैं, तो नए पृष्ठ में नई पंक्ति प्रस्तुत करें
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// पीडीएफ फाइल के पैराग्राफ संग्रह में तालिका जोड़ें
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// पीडीएफ दस्तावेज़ सहेजें
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में पेज ब्रेक कैसे डालें। आप C# का उपयोग करके PDF दस्तावेज़ में तालिका में एक निश्चित संख्या में पंक्तियों के बाद पेज ब्रेक जोड़ने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं।

### पीडीएफ फाइल में पेज ब्रेक डालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं पृष्ठ विराम के बाद बनाए गए नए पृष्ठों के लिए पृष्ठ का आकार कैसे बदल सकता हूँ?

 उत्तर: पृष्ठ विराम के बाद बनाए गए नए पृष्ठों के लिए पृष्ठ आकार बदलने के लिए, आप सेट कर सकते हैं`PageSize` की संपत्ति`Page` उदाहरण के लिए, आप पृष्ठ का आकार A4 पर सेट करने के लिए निम्न कोड का उपयोग कर सकते हैं:

```csharp
// पृष्ठ का आकार A4 पर सेट करें
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### प्रश्न: क्या मैं पृष्ठ विराम के बाद नए पृष्ठों के लिए पृष्ठ मार्जिन को नियंत्रित कर सकता हूँ?

 उत्तर: हां, आप पेज ब्रेक के बाद नए पेजों के लिए पेज मार्जिन को नियंत्रित कर सकते हैं।`Margin` की संपत्ति`Page` पेज मार्जिन सेट करने के लिए ऑब्जेक्ट। उदाहरण के लिए, सभी मार्जिन को 10 पॉइंट पर सेट करने के लिए, आप निम्न कोड का उपयोग कर सकते हैं:

```csharp
// सभी मार्जिन को 10 पॉइंट पर सेट करें
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### प्रश्न: क्या पृष्ठ विराम के बाद नए पृष्ठों में शीर्षलेख और पादलेख जोड़ना संभव है?

 उत्तर: हां, आप पेज ब्रेक के बाद नए पेजों में हेडर और फूटर जोड़ सकते हैं।`Page.Header` और`Page.Footer` पृष्ठ के शीर्षलेख और पादलेख अनुभागों में सामग्री जोड़ने के लिए गुण। उदाहरण के लिए:

```csharp
// नये पृष्ठों में हेडर जोड़ें
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// नये पृष्ठों में पादलेख जोड़ें
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### प्रश्न: क्या मैं निश्चित संख्या में पंक्तियों के अलावा अन्य विशिष्ट स्थानों पर पृष्ठ विराम सम्मिलित कर सकता हूँ?

 उत्तर: हां, आप कुछ निश्चित पंक्तियों के बाद के अलावा अन्य विशिष्ट स्थानों पर पेज ब्रेक डाल सकते हैं। आप सेट कर सकते हैं`IsInNewPage` पंक्ति की संपत्ति`true` तालिका को उस पंक्ति के बाद एक नया पृष्ठ शुरू करने के लिए बाध्य करना।

#### प्रश्न: मैं सामग्री की ऊंचाई के आधार पर पृष्ठ विराम व्यवहार को कैसे समायोजित कर सकता हूं?

 उत्तर: आप इसका उपयोग कर सकते हैं`IsBroken` तालिका की संपत्ति पृष्ठों में स्वचालित पंक्ति विभाजन को सक्षम या अक्षम करने के लिए। जब सेट किया जाता है`true`, यह सामग्री की ऊंचाई के आधार पर पंक्तियों को पृष्ठों में विभाजित करने की अनुमति देता है।