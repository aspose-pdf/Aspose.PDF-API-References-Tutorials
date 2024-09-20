---
title: शैली तालिका तत्व
linktitle: शैली तालिका तत्व
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: चरण-दर-चरण निर्देशों, कस्टम स्टाइलिंग और PDF/UA अनुपालन के साथ .NET के लिए Aspose.PDF में तालिका तत्व बनाने और स्टाइल करने का तरीका जानें।
type: docs
weight: 170
url: /hi/net/programming-with-tagged-pdf/style-table-element/
---
## परिचय

इस लेख में, हम .NET के लिए Aspose.PDF का उपयोग करके टेबल एलिमेंट बनाने और उसे स्टाइल करने के तरीके के बारे में जानेंगे। आप सीखेंगे कि टेबल की संरचना कैसे करें, कस्टम स्टाइल कैसे लागू करें और अपने दस्तावेज़ के PDF/UA अनुपालन को कैसे सत्यापित करें। इस ट्यूटोरियल के अंत तक, आप आसानी से अपने PDF में पेशेवर दिखने वाली टेबल बना पाएँगे!

## आवश्यक शर्तें

ट्यूटोरियल में शामिल होने से पहले, आपको यह सुनिश्चित करना होगा कि आपके पास निम्नलिखित चीजें हैं:

1. आपके मशीन पर Visual Studio या कोई समान IDE स्थापित होना चाहिए।
2. एप्लिकेशन चलाने के लिए .NET फ्रेमवर्क या .NET कोर SDK.
3.  Aspose.PDF for .NET लाइब्रेरी डाउनलोड की गई है और आपके प्रोजेक्ट में संदर्भित है। आप नवीनतम संस्करण यहाँ से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/net/).
4.  एक वैध Aspose लाइसेंस या[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) लाइब्रेरी की पूर्ण कार्यक्षमता को अनलॉक करने के लिए।

## पैकेज आयात करें

आरंभ करने के लिए, अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ये नामस्थान मुख्य PDF परिचालन, टैग की गई विषय-वस्तु, तालिकाएं और पाठ स्वरूपण को कवर करते हैं।

अब आइए Aspose.PDF में टेबल बनाने और स्टाइल करने की प्रक्रिया को विस्तार से समझते हैं। हम हर सेक्शन को विस्तार से देखेंगे ताकि आप उसका अनुसरण कर सकें।

## चरण 1: एक नया पीडीएफ दस्तावेज़ बनाएं और टैग की गई सामग्री सेटअप करें

इस पहले चरण में, हम एक रिक्त पीडीएफ दस्तावेज़ बनाएंगे और इसकी टैग की गई सामग्री सेट करेंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// एक नया PDF दस्तावेज़ बनाएँ
Document document = new Document();

// टैग की गई सामग्री सेटअप करें
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 हम एक नया निर्माण करके शुरू करते हैं`Document` ऑब्जेक्ट, हमारे पीडीएफ का प्रतिनिधित्व करता है।`TaggedContent`ऑब्जेक्ट का उपयोग दस्तावेज़ की संरचना को प्रबंधित करने के लिए किया जाता है, जिससे पहुँच मानकों का अनुपालन सुनिश्चित होता है। हम उचित टैगिंग के लिए दस्तावेज़ का शीर्षक और भाषा निर्धारित करते हैं।

## चरण 2: मूल तत्व को परिभाषित करें

इसके बाद, हम मूल संरचना तत्व बनाएंगे, जो हमारे पीडीएफ में सभी सामग्री के लिए कंटेनर के रूप में कार्य करता है।

```csharp
// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
```

`RootElement` हमारी तालिका सहित सभी संरचित तत्वों के लिए आधार कंटेनर के रूप में कार्य करता है। यह दस्तावेज़ के संरचनात्मक पदानुक्रम को बनाए रखने में मदद करता है, जो संगठन और पहुँच दोनों के लिए महत्वपूर्ण है।

## चरण 3: तालिका तत्व बनाएँ और उसे स्टाइल करें

 अब जब मूल तत्व स्थापित हो गया है, तो हम एक बनाएंगे`TableElement` और पृष्ठभूमि रंग, बॉर्डर और संरेखण जैसी शैलियाँ लागू करें.

```csharp
// तालिका संरचना तत्व बनाएँ
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// टेबल को स्टाइल करें
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 हम एक बनाते हैं`TableElement` , जो हमारी तालिका संरचना को परिभाषित करता है।`BackgroundColor`, `Border` , और`Alignment` गुण हमें तालिका की उपस्थिति को अनुकूलित करने की अनुमति देते हैं।`Broken` संपत्ति यह सुनिश्चित करती है कि यदि तालिका पृष्ठों में टूटती है, तो यह लंबवत टूटती है।

## चरण 4: तालिका आयाम और सेल शैलियाँ सेट करें

इस चरण में, हम स्तंभों की संख्या, सेल पैडिंग और अन्य महत्वपूर्ण तालिका गुण परिभाषित करेंगे।

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 हम यह सुनिश्चित करने के लिए कॉलम की चौड़ाई निर्दिष्ट करते हैं कि तालिका में प्रत्येक कॉलम समान रूप से स्थान पर हो।`DefaultCellBorder`, `DefaultCellPadding` , और`DefaultCellTextState` कक्षों के लिए डिफ़ॉल्ट शैलियाँ निर्धारित करें, जिनमें बॉर्डर, पैडिंग, पाठ रंग और फ़ॉन्ट आकार शामिल हैं।

## चरण 5: दोहराई जाने वाली पंक्तियाँ और कस्टम शैलियाँ जोड़ें

हम दोहराई जाने वाली पंक्तियों और अन्य विशिष्ट तालिका तत्वों जैसे शीर्षलेख और पादलेख के लिए भी शैलियाँ परिभाषित कर सकते हैं।

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

`RepeatingRowsCount` यह सुनिश्चित करता है कि यदि तालिका कई पृष्ठों में फैली हुई है तो पहली तीन पंक्तियाँ दोहराई जाएँ। हमने सेट किया`RepeatingRowsStyle` इन पंक्तियों पर कस्टम पृष्ठभूमि रंग लागू करने के लिए.

## चरण 6: टेबल हेड, बॉडी और फ़ुट तत्व जोड़ें

अब, आइए तालिका शीर्षलेख, मुख्य भाग और पादलेख अनुभाग बनाएं और उनमें सामग्री भरें।

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// शीर्षलेख पंक्ति बनाएं
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// तालिका मुख्य भाग भरें
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 तालिका तीन भागों में विभाजित है: शीर्ष, मुख्य भाग और पैर। हम सबसे पहले हेडर पंक्ति बनाते हैं`TableTHElement`और कॉलम हेडिंग जोड़ें। फिर, हम टेबल के मुख्य भाग को भरते हैं`TableTDElement`, प्रत्येक कक्ष को एक लेबल से भरना जिसमें उसकी स्थिति शामिल हो।

## चरण 7: दस्तावेज़ सहेजें

अंत में, हम पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं।

```csharp
// टैग किए गए PDF दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableElement.pdf");
```

यह चरण पीडीएफ फाइल को स्टाइल्ड तालिका के साथ सहेजकर दस्तावेज़ निर्माण प्रक्रिया को अंतिम रूप देता है।

## चरण 8: PDF/UA अनुपालन सत्यापित करें

दस्तावेज़ को सहेजने के बाद, यह सुनिश्चित करना आवश्यक है कि यह PDF/UA (यूनिवर्सल एक्सेसिबिलिटी) मानकों का अनुपालन करता है।

```csharp
// PDF/UA अनुपालन की जाँच करें
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

यहां, हम दस्तावेज़ को पुनः लोड करते हैं और इसे PDF/UA मानकों के अनुसार मान्य करते हैं। अनुपालन सुनिश्चित करता है कि आपका PDF पहुँच-योग्यता आवश्यकताओं को पूरा करता है, जिससे यह उपयोगकर्ताओं की एक विस्तृत श्रृंखला के लिए उपयुक्त हो जाता है।

## निष्कर्ष

.NET के लिए Aspose.PDF के साथ, अपने PDF दस्तावेज़ों में टेबल बनाना और स्टाइल करना सरल और सहज है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अनुकूलित शैलियों के साथ टेबल बना सकते हैं और सुनिश्चित कर सकते हैं कि आपके PDF एक्सेसिबिलिटी मानकों को पूरा करते हैं। चाहे आप रिपोर्ट बना रहे हों या संरचित दस्तावेज़ बना रहे हों, टेबल डेटा को स्पष्ट रूप से प्रस्तुत करने के लिए एक शक्तिशाली उपकरण हैं।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं तालिका कक्षों के अंदर छवियाँ जोड़ सकता हूँ?
 हां, आप तालिका कक्षों में चित्र सम्मिलित कर सकते हैं`Image` तत्व।

### मैं कॉलम की चौड़ाई को गतिशील रूप से कैसे समायोजित करूं?
 आप सेट कर सकते हैं`ColumnAdjustment` संपत्ति को`AutoFitToWindow` सामग्री के आधार पर कॉलम की चौड़ाई को स्वचालित रूप से समायोजित करने के लिए।

### क्या सभी दस्तावेजों के लिए पीडीएफ/यूए अनुपालन अनिवार्य है?
यद्यपि यह अनिवार्य नहीं है, लेकिन उच्च पहुंच मानकों की आवश्यकता वाले दस्तावेजों के लिए इसकी अनुशंसा की जाती है।

### क्या मैं विशिष्ट पंक्तियों पर अलग-अलग शैलियाँ लागू कर सकता हूँ?
 हां, आप अलग-अलग पंक्तियों या कक्षों को उनके स्थान को समायोजित करके अनुकूलित कर सकते हैं।`TextState` या`BackgroundColor`.

### टैग की गई सामग्री का उपयोग करने का क्या लाभ है?
टैग की गई सामग्री दस्तावेज़ की पहुंच में सुधार करती है और PDF/UA जैसे मानकों के अनुपालन को सुनिश्चित करने में मदद करती है।