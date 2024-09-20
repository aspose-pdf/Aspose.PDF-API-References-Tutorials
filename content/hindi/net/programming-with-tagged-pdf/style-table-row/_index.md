---
title: शैली तालिका पंक्ति
linktitle: शैली तालिका पंक्ति
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: आसानी से अपने दस्तावेज़ स्वरूपण को बढ़ाने के लिए चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.PDF का उपयोग करके PDF में तालिका पंक्तियों को स्टाइल करना सीखें।
type: docs
weight: 180
url: /hi/net/programming-with-tagged-pdf/style-table-row/
---
## परिचय

जब अच्छी तरह से संरचित और खूबसूरती से स्वरूपित पीडीएफ दस्तावेज़ बनाने की बात आती है, तो .NET के लिए Aspose.PDF एक बेहतरीन समाधान है। चाहे आप रिपोर्ट, चालान या गतिशील तालिकाएँ स्वचालित कर रहे हों, विभिन्न शैलियों के साथ तालिकाओं को स्वरूपित करना एक शानदार दस्तावेज़ की कुंजी है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.PDF का उपयोग करके तालिका पंक्ति को स्टाइल करने के बारे में गहराई से जानेंगे। और चिंता न करें, मैं आपको कदम-दर-कदम मार्गदर्शन करूँगा, बिल्कुल कॉफ़ी पर एक अच्छी बातचीत की तरह!

## आवश्यक शर्तें

इससे पहले कि हम बारीकियों में जाएं, आइए सुनिश्चित करें कि आपने अपनी सारी तैयारियां कर ली हैं। आपको चाहिए:

1. .NET लाइब्रेरी के लिए Aspose.PDF  
    यदि आपके पास यह पहले से नहीं है, तो आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/net/) . आप भी प्राप्त कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) प्रारंभ करना।
2. विकास पर्यावरण  
   Visual Studio या अपनी पसंद का कोई भी C# IDE सेट अप करें। आपको .NET इंस्टॉल करने की भी आवश्यकता होगी, लेकिन मुझे लगता है कि आप पहले से ही इससे परिचित हैं।
3. C# और .NET का बुनियादी ज्ञान  
   C# की अच्छी समझ इस ट्यूटोरियल को आसान बना देगी। लेकिन चिंता न करें, मैं प्रत्येक चरण को विस्तार से समझाऊंगा!

## पैकेज आयात करें

Aspose.PDF के साथ काम करना शुरू करने से पहले, हमें आवश्यक नेमस्पेस आयात करने की आवश्यकता है। अपने C# प्रोजेक्ट में, सुनिश्चित करें कि आपने निम्नलिखित को शामिल किया है:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ये तालिका बनाने और उसकी शैली निर्धारित करने के लिए, तथा निश्चित रूप से, अनुपालन के लिए टैग की गई सामग्री के साथ काम करने के लिए आवश्यक हैं।

अब आइए इस कार्य को चरण दर चरण समझें, ताकि आप अपनी तालिका पंक्तियों को एक पेशेवर की तरह स्टाइल कर सकें!

## चरण 1: एक नया PDF दस्तावेज़ बनाएँ

सबसे पहले: चलिए एक बिलकुल नया PDF दस्तावेज़ बनाते हैं। इस दस्तावेज़ में सभी स्टाइल्ड टेबल पंक्तियाँ होंगी।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ बनाएँ
Document document = new Document();
```

 यहाँ, हम बस एक नया आरंभ कर रहे हैं`Document` ऑब्जेक्ट जो हमारी पीडीएफ फाइल का प्रतिनिधित्व करेगा। सुनिश्चित करें कि आप उस निर्देशिका पथ को सेट करें जहाँ आप अपनी आउटपुट फ़ाइलों को सहेजेंगे।

## चरण 2: टैग की गई सामग्री के साथ काम करें

आपकी PDF को सुलभता के लिए संरचित करने के लिए, हम टैग की गई सामग्री के साथ काम करेंगे। इससे तालिकाओं जैसे संरचित तत्वों को बनाने में मदद मिलती है, यह सुनिश्चित करते हुए कि वे PDF/UA जैसे सुलभता मानकों के अनुरूप हैं।

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

यहाँ, हम PDF की टैग की गई सामग्री के लिए शीर्षक और भाषा सेट कर रहे हैं। यह आपके PDF को एक नाम देने और उसे यह बताने जैसा है कि उसे कौन सी भाषा बोलनी चाहिए!

## चरण 3: तालिका संरचना को परिभाषित करें

इसके बाद, आइए उस टेबल की संरचना को परिभाषित करें जिसे हम बनाने जा रहे हैं। हर टेबल को हेडर, बॉडी और फ़ुटर की ज़रूरत होती है - बिल्कुल एक सुव्यवस्थित ब्लॉग पोस्ट की तरह!

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

हम यहां एक हेडर के साथ एक तालिका बना रहे हैं (`THead`), शरीर (`TBody`), और पाद लेख (`TFoot`) ये तत्व हमारी पंक्तियों को धारण करने जा रहे हैं।

## चरण 4: तालिका शीर्ष पंक्ति जोड़ें

बिना हेडर वाली टेबल बिना शीर्षक वाली किताबों की तरह होती हैं। आइए डेटा के लिए संदर्भ प्रदान करने के लिए सबसे पहले हेडर पंक्ति बनाएँ।

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

यहाँ, हम लूप करते हैं और तीन हेडर सेल जोड़ते हैं (`TableTHElement`), प्रत्येक को एक वर्णनात्मक पाठ देते हुए। सरल है, है न?

## चरण 5: स्टाइल्ड बॉडी पंक्तियाँ जोड़ें

अब आता है मज़ेदार हिस्सा - पंक्तियों को स्टाइल करना! चलिए कस्टम स्टाइल के साथ सात पंक्तियाँ बनाते हैं। हम बैकग्राउंड रंग, बॉर्डर, पैडिंग और टेक्स्ट अलाइनमेंट सेट करेंगे।

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- पृष्ठभूमि का रंग: हमने पेशेवर किन्तु गर्म स्पर्श के लिए हल्के सुनहरे पीले रंग का प्रयोग किया।
- बॉर्डर: प्रत्येक पंक्ति में गहरे भूरे रंग का बाहरी बॉर्डर और तीव्र लुक के लिए नीले रंग का सेल बॉर्डर होता है।
- ऊँचाई और पैडिंग: पंक्ति की ऊँचाई निर्धारित की जाती है, और साफ़-सुथरी उपस्थिति के लिए पैडिंग जोड़ी जाती है।
- पृष्ठ विराम: तालिका को अधिक पठनीय बनाने के लिए, प्रत्येक दूसरी पंक्ति एक नये पृष्ठ पर शुरू होती है।

## चरण 6: पाद पंक्ति जोड़ें

हेडर की तरह ही फ़ुटर भी टेबल का आधार होता है। चलिए एक बनाते हैं।

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

हम बस तीन फ़ुटर सेल के माध्यम से लूप करते हैं और थोड़ा सा टेक्स्ट जोड़ते हैं। फ़ुटर के लिए वैकल्पिक टेक्स्ट "फ़ुट रो" है ताकि इसे सुलभ बनाया जा सके।

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

अब जब टेबल पूरी तरह से तैयार हो गई है, तो अपनी उत्कृष्ट कृति को सहेजने का समय आ गया है!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

ठीक इसी तरह, आपका पीडीएफ उन सभी सुंदर तालिका पंक्तियों के साथ सहेजा गया है जिन्हें हमने अभी स्टाइल किया है।

## चरण 8: PDF/UA अनुपालन सत्यापित करें

यह सुनिश्चित करने के लिए कि हमारा PDF पहुँच-योग्यता मानकों का पालन करता है, हम इसे PDF/UA अनुपालन के लिए सत्यापित करेंगे।

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

यह सुनिश्चित करता है कि आपका पीडीएफ पीडीएफ/यूए मानक को पूरा करता है, जिससे यह सभी के लिए सुलभ हो जाता है। सुलभता ही खेल का नाम है!

## निष्कर्ष

और अब यह हो गया! कोड की कुछ ही पंक्तियों के साथ, आपने .NET के लिए Aspose.PDF का उपयोग करके PDF में पूरी तरह से स्टाइल की गई टेबल बना ली है। हेडर से लेकर फ़ुटर तक, हमने प्रत्येक पंक्ति को स्टाइल किया है, एक्सेसिबिलिटी एलिमेंट जोड़े हैं, और अनुपालन के लिए दस्तावेज़ को मान्य भी किया है। चाहे आप कॉर्पोरेट रिपोर्ट, प्रेजेंटेशन पर काम कर रहे हों, या PDF के साथ मज़े कर रहे हों, यह गाइड आपके लिए है। अब, आगे बढ़ें और एक प्रो की तरह अपनी टेबल को स्टाइल करना शुरू करें!

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं तालिका की फ़ॉन्ट शैली भी बदल सकता हूँ?  
 हाँ! आप फ़ॉन्ट शैली को संशोधित कर सकते हैं`TextState` प्रत्येक सेल के लिए एक ऑब्जेक्ट, जिससे पूर्ण अनुकूलन की सुविधा मिलती है।

### मैं अपनी तालिका में और अधिक कॉलम कैसे जोड़ूं?  
 बस समायोजित करें`colCount`वेरिएबल का उपयोग करें और हेडर, बॉडी और फूटर के लिए लूप में अधिक सेल जोड़ें।

### यदि मैं पंक्ति की ऊंचाई निर्धारित नहीं करूँ तो क्या होगा?  
यदि आप पंक्ति की ऊंचाई निर्धारित नहीं करते हैं, तो तालिका सामग्री के आधार पर स्वचालित रूप से समायोजित हो जाएगी।

### क्या मैं इसे पंक्तियों की गतिशील संख्या के लिए उपयोग कर सकता हूँ?  
बिल्कुल! आप डेटाबेस या किसी अन्य स्रोत से डेटा प्राप्त कर सकते हैं और पंक्ति और कॉलम की संख्या को गतिशील रूप से समायोजित कर सकते हैं।

### क्या .NET के लिए Aspose.PDF का उपयोग निःशुल्क है?  
 .NET के लिए Aspose.PDF एक लाइसेंस प्राप्त उत्पाद है, लेकिन आप इसे आज़मा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) या प्राप्त करें[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).