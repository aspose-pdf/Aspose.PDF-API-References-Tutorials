---
title: पीडीएफ फाइल में तालिका विराम का निर्धारण करें
linktitle: पीडीएफ फाइल में तालिका विराम का निर्धारण करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में तालिका विराम निर्धारित करना सीखें।
type: docs
weight: 60
url: /hi/net/programming-with-tables/determine-table-break/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेबल ब्रेक का निर्धारण कैसे करें। हम C# में सोर्स कोड को चरण दर चरण समझाएँगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि यह कैसे निर्धारित किया जाए कि कोई टेबल पेज मार्जिन से अधिक है या नहीं। चलिए शुरू करते हैं!

## चरण 1: वातावरण की स्थापना
सबसे पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF के साथ अपना C# डेवलपमेंट एनवायरनमेंट सेट अप कर लिया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नेमस्पेस आयात करें।

## चरण 2: पीडीएफ दस्तावेज़ बनाना
 इस चरण में, हम एक नया बनाते हैं`Document` पीडीएफ दस्तावेज़ का प्रतिनिधित्व करने के लिए ऑब्जेक्ट का चयन करें।

```csharp
pdf-Document = new Document();
```

इस दस्तावेज़ का उपयोग अनुभागों और तालिकाओं को जोड़ने के लिए किया जाएगा।

## चरण 3: अनुभाग और तालिका जोड़ना
अब हम अपने पीडीएफ दस्तावेज़ में एक अनुभाग जोड़ने जा रहे हैं और इस अनुभाग के अंदर एक तालिका बनाएंगे।

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

हम तालिका के लिए 300 अंकों का शीर्ष मार्जिन भी निर्दिष्ट करते हैं। आप अपनी ज़रूरतों के हिसाब से इस मान को समायोजित कर सकते हैं।

## चरण 4: टेबल सेटअप
इस चरण में, हम तालिका गुणधर्मों को कॉन्फ़िगर करते हैं, जैसे स्तंभ की चौड़ाई और बॉर्डर।

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

यहाँ हम टेबल कॉलम की चौड़ाई और सेल बॉर्डर को परिभाषित करते हैं। आप इन मानों को अपनी पसंद के अनुसार समायोजित कर सकते हैं।

## चरण 5: तालिका में पंक्तियाँ और कक्ष जोड़ें
अब हम लूप का उपयोग करके तालिका में पंक्तियाँ और कक्ष बनाएंगे।

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

यहाँ हम तालिका में 17 पंक्तियाँ बनाते हैं और प्रत्येक पंक्ति में तीन कक्ष जोड़ते हैं। आप अपनी ज़रूरत के हिसाब से बकल को समायोजित कर सकते हैं।

## चरण 6: टेबल ब्रेक का निर्धारण
अब हम पृष्ठ की ऊंचाई की तुलना तालिका में मौजूद ऑब्जेक्ट्स की कुल ऊंचाई से करके यह निर्धारित करेंगे कि तालिका पृष्ठ मार्जिन से अधिक है या नहीं।

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

हम पृष्ठ की ऊंचाई और ऑब्जेक्ट की कुल ऊंचाई की गणना मार्जिन को ध्यान में रखते हुए करते हैं। यदि अंतर 10 या उससे कम है, तो तालिका पृष्ठ मार्जिन से अधिक हो जाती है।

## चरण 7: पीडीएफ दस्तावेज़ को सहेजना
अंत में, हम परिणामों के साथ पीडीएफ दस्तावेज़ को सेव कर लेते हैं।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

सही दस्तावेज़ निर्देशिका निर्दिष्ट करना सुनिश्चित करें। परिणामी पीडीएफ फ़ाइल निर्धारित तालिका ब्रेक के साथ सहेजी जाएगी।

### .NET के लिए Aspose.PDF का उपयोग करके तालिका विराम निर्धारित करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// ऑब्जेक्ट PDF क्लास को इंस्टैंसिएट करें
Document pdf = new Document();
// PDF दस्तावेज़ अनुभाग संग्रह में अनुभाग जोड़ें
Aspose.Pdf.Page page = pdf.Pages.Add();
// तालिका ऑब्जेक्ट को इंस्टैंसिएट करें
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// इच्छित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table1);
// तालिका की स्तंभ चौड़ाई के साथ सेट करें
table1.ColumnWidths = "100 100 100";
// BorderInfo ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// किसी अन्य अनुकूलित BorderInfo ऑब्जेक्ट का उपयोग करके तालिका बॉर्डर सेट करें
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo ऑब्जेक्ट बनाएं और उसका बायां, निचला, दायां और ऊपरी मार्जिन सेट करें
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// डिफ़ॉल्ट सेल पैडिंग को MarginInfo ऑब्जेक्ट पर सेट करें
table1.DefaultCellPadding = margin;
// यदि आप काउंटर को 17 तक बढ़ा देते हैं, तो टेबल टूट जाएगी
// क्योंकि अब इसे इस पृष्ठ पर समायोजित नहीं किया जा सकता
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// पृष्ठ ऊंचाई की जानकारी प्राप्त करें
float PageHeight = (float)pdf.PageInfo.Height;
// पृष्ठ के शीर्ष और निचले मार्जिन की कुल ऊंचाई की जानकारी प्राप्त करें,
// टेबल टॉप मार्जिन और टेबल ऊंचाई.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// पृष्ठ ऊंचाई, तालिका ऊंचाई, तालिका शीर्ष मार्जिन और पृष्ठ शीर्ष प्रदर्शित करें
// और नीचे मार्जिन जानकारी
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// जाँच करें कि क्या हम पेज टॉप मार्जिन + पेज बॉटम मार्जिन का योग घटाते हैं
// + टेबल टॉप मार्जिन और टेबल की ऊंचाई पेज की ऊंचाई से कम
// 10 से अधिक (एक औसत पंक्ति 10 से अधिक हो सकती है)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// यदि मान 10 से कम है, तो संदेश प्रदर्शित करें।
	//जो यह दर्शाता है कि एक और पंक्ति नहीं रखी जा सकती है और यदि हम नई पंक्ति जोड़ते हैं
	// पंक्ति, तालिका टूट जाएगी। यह पंक्ति ऊंचाई मान पर निर्भर करता है।
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// पीडीएफ दस्तावेज़ सहेजें
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेबल ब्रेक का निर्धारण कैसे करें। आप अपने स्वयं के C# प्रोजेक्ट में यह जाँचने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं कि कोई टेबल पेज मार्जिन से अधिक है या नहीं।

### पीडीएफ फाइल में तालिका विराम निर्धारित करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में तालिका विराम निर्धारित करने का उद्देश्य क्या है?

उत्तर: पीडीएफ दस्तावेज़ में टेबल ब्रेक का पता लगाने का उद्देश्य यह जांचना है कि क्या टेबल पेज मार्जिन से ज़्यादा है। यह सुनिश्चित करता है कि टेबल की सामग्री उपलब्ध पेज स्पेस में सही ढंग से प्रदर्शित हो। टेबल ब्रेक का पता लगाकर, आप सामग्री के अतिप्रवाह को संभाल सकते हैं और टेबल लेआउट को तदनुसार समायोजित कर सकते हैं।

#### प्रश्न: मैं तालिका के शीर्ष मार्जिन को कैसे समायोजित कर सकता हूं?

 उत्तर: दिए गए C# स्रोत कोड में, आप तालिका के शीर्ष मार्जिन को मान संशोधित करके समायोजित कर सकते हैं`table1.Margin.Top`संपत्ति। तालिका के लिए वांछित शीर्ष मार्जिन सेट करने के लिए आवश्यकतानुसार मान बढ़ाएँ या घटाएँ।

#### प्रश्न: क्या मैं तालिका के स्वरूप को अनुकूलित कर सकता हूँ, जैसे सेल रंग और फ़ॉन्ट आकार?

उत्तर: हाँ, आप .NET के लिए Aspose.PDF द्वारा प्रदान किए गए विभिन्न गुणों और विधियों का उपयोग करके तालिका और उसके कक्षों की उपस्थिति को अनुकूलित कर सकते हैं। उदाहरण के लिए, आप सेल पृष्ठभूमि रंग, फ़ॉन्ट आकार, फ़ॉन्ट परिवार, पाठ संरेखण और बहुत कुछ बदल सकते हैं। तालिका उपस्थिति को अनुकूलित करने के तरीके के बारे में अधिक जानकारी के लिए आधिकारिक दस्तावेज़ देखें।

#### प्रश्न: यदि तालिका पृष्ठ मार्जिन से अधिक हो जाए तो क्या होगा?

उत्तर: यदि तालिका पृष्ठ मार्जिन से अधिक है, तो इससे सामग्री में कटौती या ओवरलैपिंग हो सकती है, जिससे पीडीएफ दस्तावेज़ कम पठनीय और व्यवस्थित हो सकता है। तालिका के टूटने का पता लगाने और ओवरफ़्लो को संभालने से, आप यह सुनिश्चित कर सकते हैं कि सामग्री उपलब्ध पृष्ठ क्षेत्र में ठीक से प्रदर्शित रहे।

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ में एकाधिक तालिकाओं के लिए तालिका विराम निर्धारित कर सकता हूं?

उत्तर: हां, आप एक ही पीडीएफ दस्तावेज़ में कई तालिकाओं के लिए तालिका विराम निर्धारित कर सकते हैं। बस प्रत्येक तालिका के लिए चरणों को दोहराएं जिसका आप विश्लेषण करना चाहते हैं और सामग्री के अतिप्रवाह को रोकने के लिए आवश्यकतानुसार तालिका लेआउट को समायोजित करें।