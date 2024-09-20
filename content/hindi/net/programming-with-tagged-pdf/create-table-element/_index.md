---
title: तालिका तत्व बनाएँ
linktitle: तालिका तत्व बनाएँ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ एक सरणी तत्व बनाने के लिए चरण दर चरण गाइड। आसानी से तालिकाओं के साथ गतिशील PDF उत्पन्न करें।
type: docs
weight: 80
url: /hi/net/programming-with-tagged-pdf/create-table-element/
---
## परिचय

क्या आपने कभी सोचा है कि आप .NET का उपयोग करके PDF में टेबल एलिमेंट्स को आसानी से कैसे बना और कस्टमाइज़ कर सकते हैं? खैर, .NET के लिए Aspose.PDF आपका सबसे अच्छा समाधान है! चाहे आप रिपोर्ट जनरेशन को स्वचालित कर रहे हों या विभिन्न दस्तावेज़ों के लिए गतिशील रूप से टेबल बना रहे हों, Aspose.PDF टेबल एलिमेंट्स के साथ काम करने के लिए एक समृद्ध API प्रदान करता है। यह गाइड आपको चरण-दर-चरण बताएगा कि टेबल कैसे बनाएँ, उसे कैसे स्टाइल करें और यहाँ तक कि यह भी सुनिश्चित करें कि यह PDF/UA अनुपालन मानकों को पूरा करता है। रोमांचक लगता है, है न? चलिए सीधे इसमें गोता लगाते हैं!

## आवश्यक शर्तें

शुरू करने से पहले, आपको कुछ चीजों की आवश्यकता होगी:
1.  .NET के लिए Aspose.PDF: यहां से नवीनतम संस्करण डाउनलोड करें[.NET के लिए Aspose.PDF डाउनलोड करें](https://releases.aspose.com/pdf/net/).
2. विकास वातावरण: कोई भी .NET समर्थित IDE (जैसे, विज़ुअल स्टूडियो).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग से परिचित होना अनुशंसित है।

 अंत में, अपना Aspose.PDF लाइसेंस न भूलें। यदि आपके पास लाइसेंस नहीं है, तो आप इसका उपयोग कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) या अनुरोध करें[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) सब कुछ का परीक्षण करने के लिए.

## पैकेज आयात करें

सबसे पहले सबसे पहले - आइए आवश्यक पैकेज आयात करें। यह हमें PDF दस्तावेज़ों में टेबल बनाने के लिए सभी प्रासंगिक क्लासों के साथ काम करने की अनुमति देगा।

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

इस अनुभाग में, हम टेबल बनाने की प्रक्रिया को कई चरणों में विभाजित करेंगे। प्रत्येक चरण टेबल निर्माण और अनुकूलन प्रक्रिया के विभिन्न भागों पर ध्यान केंद्रित करता है।

## चरण 1: एक नया PDF दस्तावेज़ बनाएँ

सबसे पहले हमें एक नया पीडीएफ दस्तावेज़ बनाना होगा। यह हमारी टेबल के लिए कंटेनर के रूप में काम करेगा।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// एक नया PDF दस्तावेज़ बनाएँ
Document document = new Document();
```

 यहाँ, हम एक नया उदाहरण आरंभ कर रहे हैं`Document` क्लास, जो हमारी खाली पीडीएफ फाइल होगी। अपना फ़ाइल पथ परिभाषित करना न भूलें!

## चरण 2: टैग की गई सामग्री सेट करें

इसके बाद, हमें टैग की गई सामग्री को सक्षम करने की आवश्यकता है, जो तालिका के लिए पहुँच सुनिश्चित करता है। PDF/UA (यूनिवर्सल एक्सेसिबिलिटी) के अनुपालन के लिए टैग की गई PDF की आवश्यकता होती है।

```csharp
// टैग की गई सामग्री सक्षम करें
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

यह चरण दस्तावेज़ का शीर्षक और भाषा निर्धारित करता है, यह सुनिश्चित करता है कि तालिका पहुँच मानकों का अनुपालन करती है। कुछ उद्योगों में उपयोगकर्ता अनुभव और कानूनी आवश्यकताओं के लिए सुलभ दस्तावेज़ होना महत्वपूर्ण है।

## चरण 3: तालिका तत्व बनाएँ

अब आता है मज़ेदार हिस्सा - टेबल बनाना!

```csharp
// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 यहाँ, हम उपयोग कर रहे हैं`RootElement` हमारी तालिका को जोड़ने के लिए टैग की गई सामग्री का उपयोग करें। यह अनिवार्य रूप से दस्तावेज़ की संरचना में चाइल्ड नोड के रूप में एक तालिका जोड़ना है।

## चरण 4: तालिका बॉर्डर और हेडर को अनुकूलित करें

आप नहीं चाहेंगे कि आपकी टेबल नीरस दिखे, है न? चलिए इसमें कुछ स्टाइल जोड़ते हैं!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 हम बॉर्डर परिभाषित कर रहे हैं और टेबल में हेडर, बॉडी और फ़ुटर जोड़ रहे हैं। के उपयोग पर ध्यान दें`BorderInfo` तालिका की सीमाओं को गहरे नीले रंग से स्टाइल करने के लिए।

## चरण 5: तालिका में पंक्तियाँ और कक्ष जोड़ें

अब, आइए अपनी तालिका को पंक्तियों और कक्षों से भरें। प्रक्रिया का यह हिस्सा वह है जहाँ हम अपनी तालिका का लेआउट परिभाषित करते हैं।

### चरण 5.1: हेडर पंक्ति बनाएँ

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 हम 4 कॉलम वाली एक हेडर पंक्ति बना रहे हैं, और प्रत्येक हेडर सेल को पृष्ठभूमि रंग के साथ स्टाइल किया गया है`GreenYellow`हमने हेडर के लिए बॉर्डर और संरेखण भी निर्धारित किया है।

### चरण 5.2: बॉडी पंक्तियाँ जोड़ें

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

यहाँ, हम गतिशील रूप से 50 पंक्तियाँ और 4 कॉलम बना रहे हैं, उन्हें टेक्स्ट से भर रहे हैं और सेल को स्टाइल कर रहे हैं। बैकग्राउंड का रंग पीला सेट किया गया है, जिसमें टेक्स्ट बीच में है।

### चरण 5.3: पाद पंक्ति जोड़ें

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 तालिका को पूरा करने के लिए, हम केंद्रित पाठ के साथ एक पाद लेख जोड़ते हैं और`LightSeaGreen` पृष्ठभूमि।

## चरण 6: PDF/UA अनुपालन सत्यापित करें

एक बार तालिका तैयार हो जाने के बाद, यह सुनिश्चित करना महत्वपूर्ण है कि पीडीएफ पीडीएफ/यूए अनुरूप है।

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA अनुपालन सत्यापित करें
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

यह स्निपेट PDF फ़ाइल को सहेजता है और जाँचता है कि क्या यह PDF/UA अनुपालन मानकों को पूरा करता है। यदि दस्तावेज़ अनुपालन करता है, तो यह विकलांग उपयोगकर्ताओं के लिए सुलभ है।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF में सफलतापूर्वक एक पूरी तरह से अनुकूलित तालिका बनाई है। तालिका को स्टाइल करने से लेकर PDF/UA अनुपालन सुनिश्चित करने तक, अब आपके पास अपने PDF दस्तावेज़ों में गतिशील तालिकाएँ बनाने के लिए एक मज़बूत आधार है। अपने दस्तावेज़ों को और बेहतर बनाने के लिए Aspose.PDF की व्यापक विशेषताओं का पता लगाना न भूलें!

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं तालिका के फ़ॉन्ट और पाठ शैली को अनुकूलित कर सकता हूँ?
हां, Aspose.PDF आपको फ़ॉन्ट, टेक्स्ट स्टाइल और संरेखण को पूरी तरह से अनुकूलित करने की अनुमति देता है`TextState` कक्षा।

### मैं गतिशील रूप से अधिक कॉलम या पंक्तियाँ कैसे जोड़ूँ?
 आप कॉलम या पंक्तियों की संख्या को संशोधित करके समायोजित कर सकते हैं`rowIndex` और`colIndex` छोरों में.

### क्या तालिका में कोशिकाओं को मर्ज करना संभव है?
 हां, आप इसका उपयोग कर सकते हैं`ColSpan` और`RowSpan` स्तंभों या पंक्तियों में कोशिकाओं को मर्ज करने के लिए गुण।

### पीडीएफ/यूए अनुपालन क्या है?
पीडीएफ/यूए अनुपालन यह सुनिश्चित करता है कि दस्तावेज़ विकलांग उपयोगकर्ताओं के लिए सुलभ हो, तथा अंतर्राष्ट्रीय सुलभता मानकों का पालन किया जाए।

### मैं Aspose.PDF में PDF/UA अनुपालन का परीक्षण कैसे करूँ?
 आप इसका उपयोग कर सकते हैं`Validate` यह जाँचने की विधि कि क्या दस्तावेज़ पीडीएफ/यूए मानकों का अनुपालन करता है।