---
title: हेडर फ़ुटर में प्रतिस्थापन योग्य प्रतीक
linktitle: हेडर फ़ुटर में प्रतिस्थापन योग्य प्रतीक
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीकों का उपयोग करना सीखें।
type: docs
weight: 320
url: /hi/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## परिचय

पीडीएफ फाइलों के साथ काम करते समय, कई बार आपको हेडर और फूटर को पेज नंबर, रिपोर्ट नाम या जेनरेट की गई तारीखों जैसी गतिशील सामग्री के साथ कस्टमाइज़ करने की आवश्यकता होती है। सौभाग्य से, .NET के लिए Aspose.PDF इस प्रक्रिया को सरल बनाता है, जिससे आप हेडर और फूटर में स्वचालित रूप से अपडेट किए गए प्रतीकों के साथ पीडीएफ बना सकते हैं, जैसे पेज नंबर या रिपोर्ट जनरेशन विवरण। यह लेख आपको .NET के लिए Aspose.PDF का उपयोग करके हेडर और फूटर में प्रतीकों को बदलने की चरण-दर-चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा, एक ऐसे तरीके से जो न केवल सरल है बल्कि अविश्वसनीय रूप से कुशल भी है।

## आवश्यक शर्तें

चरण-दर-चरण मार्गदर्शिका में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

-  .NET लाइब्रेरी के लिए Aspose.PDF –[डाउनलोड करना](https://releases.aspose.com/pdf/net/) या प्राप्त करें[मुफ्त परीक्षण](https://releases.aspose.com/).
- आपके सिस्टम पर Visual Studio या कोई भी C# IDE स्थापित होना चाहिए।
- C# और .NET विकास का बुनियादी ज्ञान।
-  वैध[लाइसेंस](https://purchase.aspose.com/temporary-license/) Aspose.PDF के लिए, या आप परीक्षण संस्करण का उपयोग कर सकते हैं।

## पैकेज आयात करें

आरंभ करने के लिए, आपको आवश्यक नामस्थानों को आयात करना होगा जो .NET के लिए Aspose.PDF की कार्यक्षमता को सक्षम करेंगे। नीचे आवश्यक आयात है:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

ये पीडीएफ निर्माण, पाठ हेरफेर और हेडर/फुटर प्रबंधन के लिए आवश्यक हैं।

आइए उदाहरण कोड को आसानी से समझने योग्य चरणों में विभाजित करें।

## चरण 1: दस्तावेज़ और पृष्ठ सेट करें

सबसे पहले, हमें दस्तावेज़ को आरंभीकृत करना होगा और उसमें एक पृष्ठ जोड़ना होगा। यह हेडर और फ़ुटर जोड़ने के लिए आधार तैयार करता है।

```csharp
// दस्तावेज़ निर्देशिका सेट अप करें
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ ऑब्जेक्ट को आरंभ करें
Document doc = new Document();

// दस्तावेज़ में एक पृष्ठ जोड़ें
Page page = doc.Pages.Add();
```

 यहाँ, हम एक पीडीएफ दस्तावेज़ सेट कर रहे हैं`Document` क्लास और एक पेज जोड़ना`doc.Pages.Add()`इस पृष्ठ पर शीर्षलेख, पादलेख और अन्य सामग्री होगी।

## चरण 2: पेज मार्जिन कॉन्फ़िगर करें

इसके बाद, हम पृष्ठ के लिए मार्जिन निर्धारित करेंगे ताकि यह सुनिश्चित हो सके कि हमारी सामग्री किनारे तक न जाए।

```csharp
// मार्जिन कॉन्फ़िगर करें
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 यहाँ, हमने ऊपरी, निचले, बाएँ और दाएँ मार्जिन को परिभाषित किया है`MarginInfo` क्लास का उपयोग करके इसे पृष्ठ पर लागू किया`page.PageInfo.Margin`.

## चरण 3: हेडर बनाएं और कॉन्फ़िगर करें

अब, चलिए एक हेडर बनाते हैं और इसे पेज पर जोड़ते हैं। हेडर में रिपोर्ट का शीर्षक और नाम शामिल होगा।

```csharp
// हेडर बनाएं
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// हेडर मार्जिन सेट करें
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// शीर्षक में शीर्षक जोड़ें
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// हेडर में रिपोर्ट का नाम जोड़ें
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 हमने दो जोड़े हैं`TextFragment` हेडर में ऑब्जेक्ट्स: एक रिपोर्ट शीर्षक के लिए और दूसरा रिपोर्ट नाम के लिए। टेक्स्ट को स्टाइल किया जाता है`TextState` फ़ॉन्ट, आकार और संरेखण जैसे गुण.

## चरण 4: फ़ुटर बनाएँ और कॉन्फ़िगर करें

अब फ़ुटर को सेट करने का समय आ गया है, जिसमें पृष्ठ संख्या और निर्माण तिथि जैसी गतिशील सामग्री होगी।

```csharp
// फ़ुटर बनाएँ
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// फ़ुटर मार्जिन सेट करें
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// फ़ुटर सामग्री जोड़ें
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

फ़ुटर में, हम जनरेशन दिनांक, रिपोर्ट नाम और गतिशील पृष्ठ संख्या के लिए अंश शामिल करते हैं (`$p` और`$P` वर्तमान पृष्ठ संख्या और कुल पृष्ठों की संख्या को क्रमशः दर्शाते हैं)।

## चरण 5: फ़ुटर में एक तालिका बनाएँ

आप अपने डेटा को बेहतर ढंग से व्यवस्थित करने के लिए फ़ुटर में तालिकाओं जैसे अधिक जटिल तत्व भी जोड़ सकते हैं।

```csharp
// फ़ुटर के लिए तालिका बनाएँ
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// तालिका के लिए पंक्तियाँ और कक्ष बनाएँ
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// प्रत्येक सेल के लिए संरेखण सेट करें
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// तालिका कक्षों में सामग्री जोड़ें
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

यह कोड ब्लॉक फ़ूटर में 3-स्तंभ वाली तालिका बनाता है, जिसमें प्रत्येक स्तंभ में अलग-अलग जानकारी होती है, जैसे कि निर्माण तिथि, रिपोर्ट का नाम और पृष्ठ संख्या।

## चरण 6: पेज पर सामग्री जोड़ें

हेडर और फ़ुटर के अलावा, आप PDF पेज के मुख्य भाग में भी सामग्री जोड़ सकते हैं। यहाँ, हम कुछ प्लेसहोल्डर टेक्स्ट के साथ एक टेबल जोड़ते हैं।

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// तालिका सामग्री जोड़ें
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

यह कोड पेज पर तीन कॉलम वाली एक सरल तालिका जोड़ता है। आप इसे अपनी विशिष्ट आवश्यकताओं के अनुरूप संशोधित कर सकते हैं।

## चरण 7: पीडीएफ को सेव करें

एक बार सब कुछ सेट हो जाने के बाद, अंतिम चरण पीडीएफ दस्तावेज़ को अपने इच्छित स्थान पर सहेजना है।

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 आप फ़ाइल पथ निर्दिष्ट करते हैं और दस्तावेज़ को सहेजते हैं`doc.Save()`. बस! आपने कस्टमाइज़्ड हेडर और फ़ुटर के साथ सफलतापूर्वक एक पीडीएफ बना लिया है।

## निष्कर्ष

.NET के लिए Aspose.PDF का उपयोग करके हेडर और फ़ुटर में प्रतीकों को बदलना न केवल सरल है, बल्कि शक्तिशाली भी है। ऊपर दिए गए चरण-दर-चरण गाइड का पालन करके, आप आसानी से अपने PDF को गतिशील सामग्री, जैसे कि पृष्ठ संख्या, रिपोर्ट नाम और तिथियों के साथ अनुकूलित कर सकते हैं। यह विधि अत्यधिक लचीली है, जिससे आप तालिकाएँ सम्मिलित कर सकते हैं, स्वरूपण समायोजित कर सकते हैं, और अपनी विशिष्ट आवश्यकताओं के अनुरूप लेआउट को नियंत्रित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं हेडर और फ़ुटर के लिए फ़ॉन्ट अनुकूलित कर सकता हूँ?  
हां, आप हेडर और फ़ूटर में पाठ के लिए फ़ॉन्ट, आकार, रंग और शैली को पूरी तरह से अनुकूलित कर सकते हैं।

### मैं हेडर और फ़ुटर में छवियाँ कैसे जोड़ूँ?  
 आप उपयोग कर सकते हैं`ImageStamp` अपने हेडर और फूटर में चित्र सम्मिलित करने के लिए।

### क्या हेडर या फूटर में हाइपरलिंक जोड़ना संभव है?  
 हां, आप उपयोग कर सकते हैं`TextFragment` हाइपरलिंक के साथ सेट करके`Hyperlink` संपत्ति।

### क्या मैं विषम और सम पृष्ठों के लिए अलग-अलग शीर्षकों का उपयोग कर सकता हूँ?  
हां, Aspose.PDF आपको विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख निर्दिष्ट करने की अनुमति देता है।

### मैं शीर्षलेख और पादलेख की स्थिति कैसे समायोजित करूं?  
आप अपने शीर्षलेखों और पादलेखों की स्थिति को नियंत्रित करने के लिए मार्जिन और संरेखण गुणों को समायोजित कर सकते हैं।