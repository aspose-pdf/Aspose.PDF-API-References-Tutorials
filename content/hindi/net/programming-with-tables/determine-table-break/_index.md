---
title: पीडीएफ फाइल में टेबल ब्रेक निर्धारित करें
linktitle: पीडीएफ फाइल में टेबल ब्रेक निर्धारित करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में तालिका विराम निर्धारित करने का तरीका जानें।
type: docs
weight: 60
url: /hi/net/programming-with-tables/determine-table-break/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में टेबल ब्रेक कैसे निर्धारित करें। हम C# में सोर्स कोड को चरण दर चरण समझाएंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि यह कैसे निर्धारित किया जाए कि कोई तालिका पृष्ठ मार्जिन से अधिक है या नहीं। चलो शुरू करो!

## चरण 1: वातावरण स्थापित करना
सबसे पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF के साथ अपना C# विकास वातावरण स्थापित कर लिया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नामस्थान आयात करें।

## चरण 2: पीडीएफ दस्तावेज़ बनाना
 इस चरण में, हम एक नया बनाते हैं`Document` पीडीएफ दस्तावेज़ का प्रतिनिधित्व करने के लिए ऑब्जेक्ट।

```csharp
pdf-Document = new Document();
```

इस दस्तावेज़ का उपयोग अनुभागों और तालिकाओं को जोड़ने के लिए किया जाएगा।

## चरण 3: एक अनुभाग और एक तालिका जोड़ना
अब हम अपने पीडीएफ दस्तावेज़ में एक अनुभाग जोड़ने जा रहे हैं और इस अनुभाग के अंदर एक तालिका बनाएंगे।

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

हम तालिका के लिए 300 अंकों का शीर्ष मार्जिन भी निर्दिष्ट करते हैं। आप इस मान को अपनी आवश्यकताओं के अनुसार समायोजित कर सकते हैं।

## चरण 4: टेबल सेटअप
इस चरण में, हम तालिका गुणों को कॉन्फ़िगर करते हैं, जैसे कॉलम की चौड़ाई और सीमाएँ।

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

यहां हम टेबल कॉलम की चौड़ाई और सेल बॉर्डर को परिभाषित करते हैं। आप इन मानों को अपनी प्राथमिकताओं के अनुसार समायोजित कर सकते हैं।

## चरण 5: तालिका में पंक्तियाँ और कक्ष जोड़ें
अब हम लूप का उपयोग करके तालिका में पंक्तियाँ और सेल बनाएंगे।

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

यहां हम तालिका में 17 पंक्तियाँ बनाते हैं और प्रत्येक पंक्ति में तीन सेल जोड़ते हैं। आप अपनी जरूरत के हिसाब से बकल को एडजस्ट कर सकते हैं।

## चरण 6: टेबल ब्रेक का निर्धारण
अब हम तालिका में वस्तुओं की कुल ऊंचाई के साथ पृष्ठ की ऊंचाई की तुलना करके यह निर्धारित करेंगे कि तालिका पृष्ठ मार्जिन से अधिक है या नहीं।

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

हम हाशिये को ध्यान में रखते हुए पृष्ठ की ऊंचाई और वस्तुओं की कुल ऊंचाई की गणना करते हैं। यदि अंतर 10 या उससे कम है, तो तालिका पृष्ठ मार्जिन से अधिक है।

## चरण 7: पीडीएफ दस्तावेज़ को सहेजना
अंत में, हम परिणामों के साथ पीडीएफ दस्तावेज़ को सहेजते हैं।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

सही दस्तावेज़ निर्देशिका निर्दिष्ट करना सुनिश्चित करें। परिणामी पीडीएफ फाइल निर्धारित तालिका विराम के साथ सहेजी जाएगी।

### .NET के लिए Aspose.PDF का उपयोग करके टेबल ब्रेक निर्धारित करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// किसी ऑब्जेक्ट पीडीएफ क्लास को इंस्टेंट करें
Document pdf = new Document();
// अनुभाग को पीडीएफ दस्तावेज़ अनुभाग संग्रह में जोड़ें
Aspose.Pdf.Page page = pdf.Pages.Add();
// किसी तालिका ऑब्जेक्ट को त्वरित करें
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// वांछित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table1);
// तालिका की कॉलम चौड़ाई के साथ सेट करें
table1.ColumnWidths = "100 100 100";
// बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// किसी अन्य अनुकूलित बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके टेबल बॉर्डर सेट करें
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// मार्जिनइन्फो ऑब्जेक्ट बनाएं और उसके बाएँ, नीचे, दाएँ और ऊपर मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// डिफ़ॉल्ट सेल पैडिंग को मार्जिनइन्फो ऑब्जेक्ट पर सेट करें
table1.DefaultCellPadding = margin;
// यदि आप काउंटर को 17 तक बढ़ाते हैं, तो टेबल टूट जाएगी
// क्योंकि इसे अब इस पृष्ठ पर समायोजित नहीं किया जा सकता
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// तालिका में पंक्तियाँ और फिर पंक्तियों में कक्ष बनाएँ
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// पृष्ठ ऊंचाई की जानकारी प्राप्त करें
float PageHeight = (float)pdf.PageInfo.Height;
// पेज टॉप और बॉटम मार्जिन की कुल ऊंचाई की जानकारी प्राप्त करें,
// टेबल टॉप मार्जिन और टेबल ऊंचाई।
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// पृष्ठ ऊँचाई, तालिका ऊँचाई, तालिका शीर्ष मार्जिन और पृष्ठ शीर्ष प्रदर्शित करें
// और निचले मार्जिन की जानकारी
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// जांचें कि क्या हम पेज टॉप मार्जिन + पेज बॉटम मार्जिन का योग घटाते हैं
// + टेबल टॉप मार्जिन और पेज की ऊंचाई से टेबल की ऊंचाई और उससे कम
// 10 से अधिक (एक औसत पंक्ति 10 से अधिक हो सकती है)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// यदि मान 10 से कम है, तो संदेश प्रदर्शित करें।
	//जिससे पता चलता है कि दूसरी पंक्ति नहीं लगाई जा सकती और यदि हम नई जोड़ते हैं
	// पंक्ति, मेज टूट जायेगी. यह पंक्ति की ऊँचाई मान पर निर्भर करता है।
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// पीडीएफ दस्तावेज़ सहेजें
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में टेबल ब्रेक कैसे निर्धारित करें। आप इस चरण-दर-चरण मार्गदर्शिका का उपयोग यह जांचने के लिए कर सकते हैं कि कोई तालिका आपके स्वयं के C# प्रोजेक्ट में पृष्ठ मार्जिन से अधिक है या नहीं।

### पीडीएफ फाइल में टेबल ब्रेक निर्धारित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में टेबल ब्रेक निर्धारित करने का उद्देश्य क्या है?

उ: पीडीएफ दस्तावेज़ में तालिका विराम निर्धारित करने का उद्देश्य यह जांचना है कि तालिका पृष्ठ मार्जिन से अधिक है या नहीं। यह सुनिश्चित करता है कि तालिका की सामग्री उपलब्ध पृष्ठ स्थान के भीतर सही ढंग से प्रदर्शित हो। तालिका विराम का पता लगाकर, आप सामग्री अतिप्रवाह को संभाल सकते हैं और तदनुसार तालिका लेआउट को समायोजित कर सकते हैं।

#### प्रश्न: मैं तालिका के शीर्ष मार्जिन को कैसे समायोजित कर सकता हूं?

 उ: दिए गए C# स्रोत कोड में, आप के मान को संशोधित करके तालिका के शीर्ष मार्जिन को समायोजित कर सकते हैं`table1.Margin.Top`संपत्ति। तालिका के लिए वांछित शीर्ष मार्जिन सेट करने के लिए आवश्यकतानुसार मान बढ़ाएँ या घटाएँ।

#### प्रश्न: क्या मैं तालिका के स्वरूप, जैसे सेल रंग और फ़ॉन्ट आकार, को अनुकूलित कर सकता हूँ?

उत्तर: हाँ, आप .NET के लिए Aspose.PDF द्वारा प्रदान की गई विभिन्न संपत्तियों और विधियों का उपयोग करके तालिका और उसके कक्षों के स्वरूप को अनुकूलित कर सकते हैं। उदाहरण के लिए, आप सेल पृष्ठभूमि रंग, फ़ॉन्ट आकार, फ़ॉन्ट परिवार, टेक्स्ट संरेखण और बहुत कुछ बदल सकते हैं। तालिका के स्वरूप को अनुकूलित करने के तरीके के बारे में अधिक जानकारी के लिए आधिकारिक दस्तावेज़ देखें।

#### प्रश्न: यदि तालिका पृष्ठ मार्जिन से अधिक हो जाए तो क्या होगा?

उ: यदि तालिका पृष्ठ मार्जिन से अधिक है, तो इसके परिणामस्वरूप सामग्री में कटौती या ओवरलैपिंग हो सकती है, जिससे पीडीएफ दस्तावेज़ कम पठनीय और व्यवस्थित हो जाएगा। तालिका टूटने का पता लगाकर और अतिप्रवाह को संभालकर, आप यह सुनिश्चित कर सकते हैं कि सामग्री उपलब्ध पृष्ठ क्षेत्र में ठीक से प्रदर्शित होती रहे।

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ में एकाधिक तालिकाओं के लिए तालिका विराम निर्धारित कर सकता हूँ?

उ: हां, आप एक ही पीडीएफ दस्तावेज़ में एकाधिक तालिकाओं के लिए तालिका विराम निर्धारित कर सकते हैं। जिस प्रत्येक तालिका का आप विश्लेषण करना चाहते हैं उसके लिए बस चरणों को दोहराएं और सामग्री अतिप्रवाह को रोकने के लिए आवश्यकतानुसार तालिका लेआउट को समायोजित करें।