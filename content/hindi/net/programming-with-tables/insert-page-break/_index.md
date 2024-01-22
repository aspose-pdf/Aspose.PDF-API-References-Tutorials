---
title: पीडीएफ फाइल में पेज ब्रेक डालें
linktitle: पीडीएफ फाइल में पेज ब्रेक डालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पेज ब्रेक डालने का तरीका जानें।
type: docs
weight: 110
url: /hi/net/programming-with-tables/insert-page-break/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में पेज ब्रेक कैसे डालें। हम C# में सोर्स कोड को चरण दर चरण समझाएंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि पीडीएफ दस्तावेज़ की तालिका में एक निश्चित संख्या में पंक्तियों के बाद पेज ब्रेक कैसे जोड़ा जाता है। चलो शुरू करो!

## चरण 1: वातावरण स्थापित करना
सुनिश्चित करें कि आपने अपने C# विकास परिवेश को .NET के लिए Aspose.PDF के साथ कॉन्फ़िगर किया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नामस्थान आयात करें।

## चरण 2: दस्तावेज़ और तालिका बनाना
हम एक नया दस्तावेज़ उदाहरण बनाते हैं और इस दस्तावेज़ में एक पृष्ठ जोड़ते हैं। इसके बाद, हम पीडीएफ दस्तावेज़ में अपनी तालिका का प्रतिनिधित्व करने के लिए एक तालिका उदाहरण बनाते हैं। हम तालिका के लिए बॉर्डर शैलियों को भी परिभाषित करते हैं।

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## चरण 3: तालिका में पंक्तियाँ जोड़ें
हम सरणी में 200 पंक्तियाँ जोड़ने के लिए एक लूप का उपयोग करते हैं। प्रत्येक पंक्ति के लिए, हम पंक्ति का एक उदाहरण बनाते हैं और पाठ सामग्री के साथ दो सेल जोड़ते हैं।

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
हम तालिका को दस्तावेज़ पृष्ठ के पैराग्राफ संग्रह में जोड़ते हैं।

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## चरण 5: दस्तावेज़ सहेजें
हम पेज ब्रेक डालकर पीडीएफ दस्तावेज़ को सहेजते हैं।

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके पेज ब्रेक सम्मिलित करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// त्वरित दस्तावेज़ उदाहरण
Document doc = new Document();
// पीडीएफ फाइल के पेज संग्रह में पेज जोड़ें
doc.Pages.Add();
// तालिका उदाहरण बनाएँ
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// तालिका के लिए बॉर्डर शैली सेट करें
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// तालिका के लिए बॉर्डर रंग के साथ लाल के रूप में डिफ़ॉल्ट बॉर्डर शैली सेट करें
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// तालिका कॉलम की चौड़ाई निर्दिष्ट करें
tab.ColumnWidths = "100 100";
// तालिका में 200 पंक्तियाँ जोड़ने के लिए एक लूप बनाएँ
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// जब 10 पंक्तियाँ जोड़ी जाती हैं, तो नई पंक्ति को नए पृष्ठ में प्रस्तुत करें
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में पेज ब्रेक कैसे डाला जाए। आप C# का उपयोग करके किसी पीडीएफ दस्तावेज़ में तालिका में एक निश्चित संख्या में पंक्तियों के बाद पेज ब्रेक जोड़ने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं।

### पीडीएफ फाइल में पेज ब्रेक डालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पेज ब्रेक के बाद बनाए गए नए पेजों के लिए मैं पेज का आकार कैसे बदल सकता हूं?

 उ: पेज ब्रेक के बाद बनाए गए नए पेजों के लिए पेज का आकार बदलने के लिए, आप सेट कर सकते हैं`PageSize` की संपत्ति`Page` वस्तु। उदाहरण के लिए, आप पृष्ठ का आकार A4 पर सेट करने के लिए निम्नलिखित कोड का उपयोग कर सकते हैं:

```csharp
// पेज का आकार A4 पर सेट करें
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### प्रश्न: क्या मैं पेज ब्रेक के बाद नए पेजों के लिए पेज मार्जिन को नियंत्रित कर सकता हूँ?

 उ: हां, आप पेज ब्रेक के बाद नए पेजों के लिए पेज मार्जिन को नियंत्रित कर सकते हैं। उपयोग`Margin` की संपत्ति`Page` पेज मार्जिन सेट करने के लिए ऑब्जेक्ट। उदाहरण के लिए, सभी मार्जिन को 10 अंक पर सेट करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```csharp
// सभी मार्जिन को 10 अंक पर सेट करें
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### प्रश्न: क्या पृष्ठ विराम के बाद नए पृष्ठों में शीर्षलेख और पादलेख जोड़ना संभव है?

 उ: हाँ, आप पृष्ठ विराम के बाद नए पृष्ठों में शीर्षलेख और पादलेख जोड़ सकते हैं। उपयोग`Page.Header` और`Page.Footer` पृष्ठ के शीर्ष लेख और पाद लेख अनुभागों में सामग्री जोड़ने के लिए गुण। उदाहरण के लिए:

```csharp
// नए पेजों में हेडर जोड़ें
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// नए पृष्ठों में पाद लेख जोड़ें
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### प्रश्न: क्या मैं पंक्तियों की एक निश्चित संख्या के अलावा विशिष्ट स्थानों पर पृष्ठ विराम सम्मिलित कर सकता हूँ?

 उ: हाँ, आप पंक्तियों की एक निश्चित संख्या के अलावा विशिष्ट स्थानों पर पृष्ठ विराम सम्मिलित कर सकते हैं। आप सेट कर सकते हैं`IsInNewPage` एक पंक्ति की संपत्ति`true` तालिका को उस पंक्ति के बाद एक नया पृष्ठ प्रारंभ करने के लिए बाध्य करना।

#### प्रश्न: मैं सामग्री की ऊंचाई के आधार पर पेज ब्रेक व्यवहार को कैसे समायोजित कर सकता हूं?

उत्तर: आप इसका उपयोग कर सकते हैं`IsBroken` पृष्ठों में स्वचालित पंक्ति विभाजन को सक्षम या अक्षम करने के लिए तालिका की संपत्ति। जब सेट किया जाए`true`, यह सामग्री की ऊंचाई के आधार पर पंक्तियों को पृष्ठों में विभाजित करने की अनुमति देता है।