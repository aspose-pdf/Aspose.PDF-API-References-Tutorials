---
title: लिंक संरचना तत्व
linktitle: लिंक संरचना तत्व
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF में लिंक संरचना तत्व बनाने का तरीका जानें। सुलभ लिंक, छवियाँ और अनुपालन सत्यापन जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 120
url: /hi/net/programming-with-tagged-pdf/link-structure-elements/
---
## परिचय

PDF में लिंक संरचना तत्वों को बनाना और प्रबंधित करना उन दस्तावेज़ों के लिए महत्वपूर्ण हो सकता है जिनमें पहुँच और सहज नेविगेशन की आवश्यकता होती है। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके ऐसा करने का तरीका बताएँगे। यदि आप Aspose.PDF या सामान्य रूप से PDF हेरफेर के लिए नए हैं, तो चिंता न करें। मैं हर चरण को विस्तार से समझाऊँगा ताकि आप आसानी से उसका अनुसरण कर सकें!

## आवश्यक शर्तें  

कोडिंग में उतरने से पहले, आइए कुछ बातें पहले ही समझ लें। एक सहज विकास अनुभव सुनिश्चित करने के लिए ये बुनियादी ज़रूरतें हैं।

1.  .NET के लिए Aspose.PDF: आप नवीनतम संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/pdf/net/).
2. .NET विकास वातावरण: चाहे वह विजुअल स्टूडियो हो या कोई भी .NET-संगत IDE, इसे स्थापित और तैयार रखें।
3.  Aspose लाइसेंस: आप Aspose.PDF के निःशुल्क परीक्षण संस्करण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/) या प्राप्त करें[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).
4. C# का बुनियादी ज्ञान: हम कुछ C# कोड के साथ काम करेंगे, इसलिए बुनियादी बातों को समझने से चीजें बहुत आसान हो जाएंगी।

## पैकेज आयात करें

लिंक संरचना तत्वों के लिए कोड लिखने से पहले आपको कुछ पैकेज आयात करने होंगे। अपने प्रोजेक्ट में आवश्यक Aspose.PDF लाइब्रेरीज़ को संदर्भित करके शुरू करें:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ये आयात हमें पीडीएफ दस्तावेजों के साथ काम करने, टैग जोड़ने और संरचना तत्वों का प्रबंधन करने में सक्षम बनाते हैं।

अब हम विभिन्न प्रकार की लिंक संरचनाओं के साथ एक पीडीएफ दस्तावेज़ तैयार करेंगे, और प्रक्रिया को अच्छी तरह से समझने में आपकी सहायता के लिए प्रत्येक चरण को विभाजित किया जाएगा।

## चरण 1: दस्तावेज़ को आरंभ करें  

आइए एक नया पीडीएफ दस्तावेज़ बनाकर और सुलभता के लिए टैग की गई सामग्री सेट करके शुरुआत करें।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// एक नया PDF दस्तावेज़ बनाएँ
Document document = new Document(); 

// TaggedContent इंटरफ़ेस पुनः प्राप्त करें
ITaggedContent taggedContent = document.TaggedContent;
```
  
 यहाँ, हम आरंभ कर रहे हैं`Document` ऑब्जेक्ट, जो हमारी पीडीएफ फाइल का प्रतिनिधित्व करता है। हम इसे भी पुनः प्राप्त करते हैं`TaggedContent` इंटरफ़ेस, हमें पैराग्राफ, लिंक और छवियों जैसे संरचना तत्वों को जोड़ने की अनुमति देता है।

## चरण 2: शीर्षक और भाषा सेट करें  

प्रत्येक पीडीएफ में शीर्षक और भाषा सेटिंग होनी चाहिए, खासकर यदि आप पीडीएफ/यूए मानकों के अनुपालन का लक्ष्य बना रहे हैं।

```csharp
// दस्तावेज़ का शीर्षक और भाषा सेट करें
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
यह चरण सुनिश्चित करता है कि आपके पीडीएफ का शीर्षक सार्थक हो और भाषा अंग्रेजी में सेट हो (`en-US`) यह पहुंच के लिए महत्वपूर्ण है और यह सुनिश्चित करता है कि स्क्रीन रीडर या अन्य सहायक प्रौद्योगिकियां आपके दस्तावेज़ को सही ढंग से समझ सकें।

## चरण 3: पैराग्राफ़ बनाएँ और जोड़ें  

इस चरण में, हम अपने लिंक तत्वों को रखने के लिए पैराग्राफ जोड़ेंगे।

```csharp
// मूल तत्व बनाएँ
StructureElement rootElement = taggedContent.RootElement;

// एक पैराग्राफ़ बनाएँ और उसे मूल तत्व में जोड़ें
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
हम एक मूल संरचना तत्व बनाते हैं, जो अनिवार्य रूप से अन्य सभी तत्वों के लिए शीर्ष-स्तरीय कंटेनर है। फिर हम एक पैराग्राफ बनाते हैं (`p1`) और इसे मूल तत्व में जोड़ें.

## चरण 4: एक सरल लिंक जोड़ें  

अब आइए एक बुनियादी हाइपरलिंक जोड़ें जो गूगल की ओर इंगित करता है।

```csharp
// एक लिंक तत्व बनाएं और उसे पैराग्राफ़ में जोड़ें
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// लिंक के लिए हाइपरलिंक और टेक्स्ट सेट करें
link1.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
इस चरण में, हमने एक लिंक तत्व बनाया, उसका हाइपरलिंक "http://google.com" पर सेट किया, और लिंक के लिए टेक्स्ट ("Google") प्रदान किया। हमने पहुँच सुनिश्चित करने के लिए एक वैकल्पिक विवरण भी जोड़ा।

## चरण 5: स्पैन के साथ लिंक जोड़ना  

हम पाठ के विभिन्न विस्तारों के साथ लिंक भी बना सकते हैं।

```csharp
// एक और पैराग्राफ़ बनाएँ
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// स्पैन तत्व के साथ एक लिंक बनाएं
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://गूगल.कॉम");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
यहां, हमने लिंक के भीतर पाठ के एक हिस्से को शामिल करने के लिए स्पैन तत्व का उपयोग किया है, जिससे हमें लिंक के कुछ हिस्सों को प्रदर्शित करने के तरीके को अनुकूलित करने की अनुमति मिलती है।

## चरण 6: मल्टीलाइन लिंक  

अगर आपका लिंक टेक्स्ट बहुत लंबा है तो क्या होगा? चिंता न करें, आप इसे कई लाइनों में बांट सकते हैं।

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
इस मामले में, हमने केवल एक लंबा टेक्स्ट मान सेट करके एक मल्टीलाइन लिंक बनाया है, और टेक्स्ट स्वचालित रूप से कई पंक्तियों में लपेटा जाएगा।

## चरण 7: लिंक में एक छवि जोड़ें  

अंत में, आप लिंक के अंदर चित्र भी जोड़ सकते हैं।

```csharp
// एक नया पैराग्राफ़ और लिंक तत्व बनाएँ
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://गूगल.कॉम");

// लिंक में एक छवि जोड़ें
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
यह चरण दर्शाता है कि आप अपने लिंक को इमेज के साथ कैसे बेहतर बना सकते हैं। इस मामले में, हमने लिंक के अंदर एक Google आइकन जोड़ा। हमने इमेज के लिए वैकल्पिक टेक्स्ट सेट करके पहुँच सुनिश्चित की।

## चरण 8: अनुपालन के लिए पीडीएफ को मान्य करें  

यदि आप PDF/UA अनुपालन (एक सुलभता मानक) का लक्ष्य रख रहे हैं, तो अपने दस्तावेज़ को मान्य करना अच्छा अभ्यास है।

```csharp
// पीडीएफ दस्तावेज़ सहेजें
document.Save(outFile);

// PDF/UA अनुपालन के लिए दस्तावेज़ को मान्य करें
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
हमने दस्तावेज़ को सहेज लिया और इसे PDF/UA मानक के अनुरूप सत्यापित किया, जिससे यह सुनिश्चित हो गया कि PDF पहुँच-योग्यता आवश्यकताओं को पूरा करता है।

## निष्कर्ष  

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.PDF का उपयोग करके संरचित PDF दस्तावेज़ बनाने का तरीका बताया है। बुनियादी हाइपरलिंक जोड़ने से लेकर स्पैन, मल्टीलाइन लिंक और यहां तक कि छवियों जैसी अधिक जटिल संरचनाओं तक, यह गाइड आपके PDF में लिंक तत्वों में हेरफेर करने के लिए एक ठोस आधार प्रदान करता है। PDF/UA अनुपालन के अतिरिक्त लाभ के साथ, अब आप सुलभ और नेविगेट करने योग्य PDF बनाने के लिए सुसज्जित हैं।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं लिंक के अंदर तालिकाओं जैसी अधिक जटिल संरचनाएं जोड़ सकता हूं?  
नहीं, लिंक मुख्यतः पाठ और छवियों के लिए होते हैं, लेकिन आप जटिल तत्वों को भी पास में एम्बेड कर सकते हैं।

### क्या PDF/UA सत्यापन अनिवार्य है?  
हमेशा नहीं, लेकिन यदि आप पहुंच-योग्यता के बारे में चिंतित हैं तो यह अत्यधिक अनुशंसित है।

### यदि छवि फ़ाइल पथ गलत है तो क्या होगा?  
दस्तावेज़ छवि प्रदर्शित नहीं करेगा, तथा रेंडरिंग के दौरान त्रुटि उत्पन्न हो सकती है।

### क्या मैं लिंक के भीतर पाठ को स्टाइल कर सकता हूँ?  
हां, आप स्पैन तत्वों का उपयोग करके पाठ शैलियाँ लागू कर सकते हैं।

### क्या आंतरिक दस्तावेज़ लिंक बनाना संभव है?  
बिल्कुल! आप एक ही दस्तावेज़ के भीतर विशिष्ट अनुभागों से लिंक कर सकते हैं।