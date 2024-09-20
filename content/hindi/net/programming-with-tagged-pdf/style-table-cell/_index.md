---
title: स्टाइल टेबल सेल
linktitle: स्टाइल टेबल सेल
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस विस्तृत ट्यूटोरियल के साथ .NET के लिए Aspose.PDF का उपयोग करके PDF में टेबल सेल को स्टाइल करना सीखें। सुंदर PDF टेबल बनाने और फ़ॉर्मेट करने के लिए निर्देशों का पालन करें।
type: docs
weight: 160
url: /hi/net/programming-with-tagged-pdf/style-table-cell/
---
## परिचय

पेशेवर दिखने वाली PDF टेबल बनाना मुश्किल हो सकता है, लेकिन .NET के लिए Aspose.PDF के साथ, यह आश्चर्यजनक रूप से सरल है! चाहे आप हेडर, फ़ुटर या विशिष्ट टेबल सेल को स्टाइल कर रहे हों, यह शक्तिशाली लाइब्रेरी आपको सुंदर स्वरूपित PDF दस्तावेज़ बनाने के लिए आवश्यक सभी उपकरण प्रदान करती है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेबल सेल को स्टाइल करने का तरीका बताएंगे। चिंता न करें - हम सब कुछ आसान-से-पालन चरणों में विभाजित करेंगे।

## आवश्यक शर्तें

कोड में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

1. .NET के लिए Aspose.PDF: Aspose.PDF का नवीनतम संस्करण यहाँ से डाउनलोड करें और इंस्टॉल करें[यहाँ](https://releases.aspose.com/pdf/net/).
2. IDE (जैसे Visual Studio): .NET विकास वातावरण स्थापित करें।
3. C# प्रोग्रामिंग का बुनियादी ज्ञान: C# से थोड़ी परिचितता आवश्यक है।
4.  Aspose.PDF लाइसेंस: लाइब्रेरी की सभी सुविधाओं को अनलॉक करने के लिए एक अस्थायी या पूर्ण लाइसेंस प्राप्त करें। आप एक निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

## पैकेज आयात करें

शुरू करने से पहले, ज़रूरी नेमस्पेस को आयात करना सुनिश्चित करें। आपको अपने प्रोजेक्ट में निम्नलिखित की ज़रूरत होगी:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

अब जब सब कुछ सेट हो गया है, तो चलिए चरण-दर-चरण मार्गदर्शिका पर चलते हैं!

हम एक पीडीएफ दस्तावेज़ में एक टेबल बनाने जा रहे हैं और उसके सेल को स्टाइल करेंगे। प्रत्येक चरण में प्रक्रिया को विस्तार से समझाया जाएगा।

## चरण 1: एक नया PDF दस्तावेज़ बनाएँ

 पहला कदम एक नया पीडीएफ दस्तावेज़ बनाना है। Aspose.PDF में, आप एक नया पीडीएफ दस्तावेज़ आरंभ कर सकते हैं।`Document` ऑब्जेक्ट, जो आपकी पीडीएफ फाइल का प्रतिनिधित्व करता है.

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// एक नया PDF दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

यहाँ, हम एक PDF दस्तावेज़ को आरंभ करते हैं और उसका शीर्षक और भाषा सेट करते हैं। यह आपके दस्तावेज़ को एक उचित संरचना देता है, जो PDF/UA अनुपालन के लिए आवश्यक है।

## चरण 2: तालिका संरचना सेट करें

पीडीएफ में तालिकाएँ संरचना तत्वों के भीतर परिभाषित की जाती हैं। आइए तालिका बनाएँ और तालिका की पंक्तियों और स्तंभों को परिभाषित करें।

```csharp
// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// तालिका संरचना तत्व बनाएँ
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

हमने अब तालिका का शीर्ष (`TableTHeadElement`), शरीर (`TableTBodyElement`), और पैर (`TableTFootElement`) अनुभाग। आप इन्हें अपनी तालिका के ढांचे के रूप में सोच सकते हैं।

## चरण 3: हेडर सेल को स्टाइल करें

हेडर सेल को स्टाइल करने से वे अलग दिखते हैं। यहाँ, हम बैकग्राउंड रंग, बॉर्डर और टेक्स्ट अलाइनमेंट लागू करते हैं।

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

इस चरण में, हम प्रत्येक हेडर सेल को लूप करते हैं, जिससे उसे हरा-पीला बैकग्राउंड, ग्रे बॉर्डर और दाएं-संरेखित टेक्स्ट मिलता है। आप इन गुणों को अपने इच्छित डिज़ाइन से मेल खाने के लिए समायोजित कर सकते हैं।

## चरण 4: तालिका बॉडी को पॉप्युलेट और स्टाइल करें

टेबल बॉडी में वास्तविक डेटा होता है। यहां बताया गया है कि आप प्रत्येक सेल को विशिष्ट मार्जिन, बॉर्डर और टेक्स्ट सेटिंग के साथ कैसे स्टाइल कर सकते हैं।

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 इस चरण में, हम टेबल बॉडी को चार पंक्तियों से भरते हैं और प्रत्येक सेल को पीले रंग की पृष्ठभूमि और केंद्र में बोल्ड नीले रंग के टेक्स्ट से स्टाइल करते हैं।`MarginInfo`पाठ के चारों ओर पैडिंग को परिभाषित करने के लिए क्लास का उपयोग करें।

## चरण 5: फ़ुटर को स्टाइल करें

तालिका को पूर्ण संरचना देने के लिए, हम पाद लेख कक्षों को जोड़ते हैं और उनकी शैली निर्धारित करते हैं, ठीक उसी तरह जैसे हमने शीर्ष लेख के साथ किया था।

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

पाद लेख अनुभाग की शैली शीर्ष लेख के समान ही होती है, जिससे पाठकों के लिए तालिका की संरचना का अनुसरण करना आसान हो जाता है।

## चरण 6: पीडीएफ दस्तावेज़ को सहेजें और मान्य करें

अंत में, हम पीडीएफ दस्तावेज़ को सेव करते हैं और जांचते हैं कि यह पीडीएफ/यूए अनुरूप है या नहीं।

```csharp
// टैग किए गए PDF दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA अनुपालन की जाँच करना
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 हम पीडीएफ को सेव करते हैं और उसका उपयोग करते हैं`Validate` यह सुनिश्चित करने के लिए कि यह पहुँच योग्यता मानकों (पीडीएफ/यूए अनुपालन) को पूरा करता है।

## निष्कर्ष

.NET के लिए Aspose.PDF का उपयोग करके PDF में टेबल को स्टाइल करना शक्तिशाली और लचीला दोनों है। कोड की कुछ पंक्तियों के साथ, आप कस्टम टेबल डिज़ाइन बना सकते हैं जो आपके PDF दस्तावेज़ों को अलग बना देगा। सेल बॉर्डर और बैकग्राउंड को कस्टमाइज़ करने से लेकर एक्सेसिबिलिटी अनुपालन सुनिश्चित करने तक, Aspose.PDF पॉलिश की गई PDF फ़ाइलें बनाना आसान बनाता है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं अलग-अलग तालिका कक्षों पर अलग-अलग शैलियाँ लागू कर सकता हूँ?  
हां, आप अलग-अलग कक्षों को अनुकूलित करके स्टाइल दे सकते हैं`TableTDElement` गुण।

### मैं तालिका कक्षों को कैसे मर्ज कर सकता हूँ?  
 आप इसका उपयोग कर सकते हैं`ColSpan` और`RowSpan` तालिका में कक्षों को मर्ज करने के लिए गुण.

### क्या PDF/UA अनुरूप तालिका बनाना संभव है?  
 हां, जैसा कि इस गाइड में दिखाया गया है, आप अपने दस्तावेज़ को सत्यापित करके पीडीएफ/यूए अनुपालन सुनिश्चित कर सकते हैं`Validate` तरीका।

### क्या मैं तालिका कक्षों में अलग-अलग फ़ॉन्ट का उपयोग कर सकता हूँ?  
 बिल्कुल! आप इसका उपयोग करके अलग-अलग फ़ॉन्ट निर्दिष्ट कर सकते हैं`TextState` प्रत्येक कक्ष के लिए ऑब्जेक्ट.

### मैं .NET के लिए Aspose.PDF कैसे डाउनलोड करूं?  
 आप इसे यहाँ से डाउनलोड कर सकते हैं[विज्ञप्ति पृष्ठ](https://releases.aspose.com/pdf/net/).