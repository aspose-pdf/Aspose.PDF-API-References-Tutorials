---
title: लिंक संरचना तत्व
linktitle: लिंक संरचना तत्व
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ लिंक संरचना तत्वों का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका। अपने PDF दस्तावेज़ों में हाइपरलिंक बनाएँ।
type: docs
weight: 120
url: /hi/net/programming-with-tagged-pdf/link-structure-elements/
---
इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि .NET के लिए Aspose.PDF के साथ लिंक संरचना तत्वों का उपयोग कैसे करें। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने और उनमें हेरफेर करने की सुविधा देती है। लिंक संरचना तत्व आपको अपने PDF दस्तावेज़ में हाइपरलिंक जोड़ने की अनुमति देते हैं, जिससे उपयोगकर्ता लिंक पर क्लिक करके ऑनलाइन संसाधनों पर नेविगेट कर सकते हैं।

आइए कोड में गोता लगाएँ और सीखें कि .NET के लिए Aspose.PDF के साथ लिंक संरचना तत्वों का उपयोग कैसे करें।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. .NET के लिए Aspose.PDF लाइब्रेरी स्थापित।
2. C# प्रोग्रामिंग भाषा का मूलभूत ज्ञान।

## चरण 1: वातावरण की स्थापना

आरंभ करने के लिए, अपना C# डेवलपमेंट एनवायरनमेंट खोलें और एक नया प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.PDF लाइब्रेरी का संदर्भ जोड़ा है।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## चरण 2: दस्तावेज़ बनाना

 पहला कदम का उपयोग कर एक नया पीडीएफ दस्तावेज़ बनाना है`Document` कक्षा।

```csharp
// पीडीएफ दस्तावेज़ बनाएं
Document document = new Document();
```

## चरण 3: टैग की गई सामग्री के साथ काम करें

फिर हमें कार्य करने के लिए दस्तावेज़ की टैग की गई सामग्री मिलती है।

```csharp
// दस्तावेज़ की टैग की गई सामग्री प्राप्त करें
ITaggedContent taggedContent = document.TaggedContent;
```

## चरण 4: दस्तावेज़ का शीर्षक और भाषा सेट करें

अब हम दस्तावेज़ का शीर्षक और भाषा निर्धारित कर सकते हैं।

```csharp
// दस्तावेज़ का शीर्षक और भाषा निर्धारित करें
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## चरण 5: लिंक संरचना तत्व जोड़ें

अब आइए अपने दस्तावेज़ में लिंक संरचना तत्व जोड़ें। हम विभिन्न प्रकार के लिंक बनाएंगे, जिसमें सरल टेक्स्ट लिंक, छवि लिंक और मल्टी-लाइन लिंक शामिल हैं।
```csharp
// मूल संरचना तत्व (दस्तावेज़ संरचना तत्व) प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// हाइपरलिंक के साथ पैराग्राफ़ जोड़ें
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// रिच टेक्स्ट वाले हाइपरलिंक के साथ पैराग्राफ़ जोड़ें
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// आंशिक रूप से स्वरूपित पाठ वाले हाइपरलिंक के साथ पैराग्राफ़ जोड़ें
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// मल्टीलाइन हाइपरलिंक के साथ पैराग्राफ़ जोड़ें
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// एक छवि वाले हाइपरलिंक के साथ एक पैराग्राफ जोड़ें
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## चरण 6: टैग किए गए PDF दस्तावेज़ को सहेजें

अंत में, हम टैग किए गए पीडीएफ दस्तावेज़ को सेव कर लेते हैं।

```csharp
// टैग किए गए PDF दस्तावेज़ को सहेजें
document. Save(outFile);
```

## चरण 7: PDF/UA अनुपालन की जाँच करें

 हम PDF/UA अनुपालन के लिए दस्तावेज़ की जांच भी कर सकते हैं`Validate` की विधि`Document` कक्षा।

```csharp
// PDF/UA अनुपालन की जाँच करें
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### .NET के लिए Aspose.PDF का उपयोग करके लिंक संरचना तत्वों के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// दस्तावेज़ बनाना और टैग की गई पीडीएफ सामग्री प्राप्त करना
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// दस्तावेज़ के लिए शीर्षक और प्रकृति भाषा सेट करना
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// रूट संरचना तत्व (दस्तावेज़ संरचना तत्व) प्राप्त करना
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://गूगल.कॉम");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// टैग किए गए पीडीएफ दस्तावेज़ सहेजें
document.Save(outFile);

// PDF/UA अनुपालन की जाँच करना
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF के साथ लिंक संरचना तत्वों का उपयोग करना सीख लिया है। अब आप अपने PDF दस्तावेज़ों में हाइपरलिंक बना सकते हैं, जिससे उपयोगकर्ता ऑनलाइन संसाधनों पर नेविगेट कर सकते हैं। इंटरैक्टिव और समृद्ध PDF दस्तावेज़ बनाने के लिए Aspose.PDF की अधिक सुविधाओं का प्रयोग करें और उनका अन्वेषण करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में लिंक संरचना तत्व क्या हैं, और वे दस्तावेज़ की अन्तरक्रियाशीलता को कैसे बढ़ाते हैं?

उत्तर: पीडीएफ दस्तावेज़ में लिंक संरचना तत्वों का उपयोग हाइपरलिंक बनाने के लिए किया जाता है जो उपयोगकर्ताओं को दस्तावेज़ के भीतर ऑनलाइन संसाधनों या विशिष्ट स्थानों पर नेविगेट करने की अनुमति देता है। ये तत्व क्लिक करने योग्य लिंक प्रदान करके अन्तरक्रियाशीलता को बढ़ाते हैं जो उपयोगकर्ताओं को संबंधित सामग्री या बाहरी वेबसाइटों तक पहुँचने में सक्षम बनाते हैं।

#### प्रश्न: पीडीएफ दस्तावेज़ में लिंक संरचना तत्व किस प्रकार लाभकारी हो सकते हैं?

उत्तर: लिंक संरचना तत्व पीडीएफ दस्तावेज़ को इंटरैक्टिव बनाकर उपयोगकर्ता अनुभव को बेहतर बनाते हैं। वे अतिरिक्त जानकारी, संबंधित सामग्री, बाहरी वेबसाइटों या दस्तावेज़ के भीतर विशिष्ट अनुभागों तक त्वरित पहुँच प्रदान करते हैं, नेविगेशन में सुधार करते हैं और सूचना पुनर्प्राप्ति को सुविधाजनक बनाते हैं।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF में लिंक संरचना तत्वों का उपयोग करके विभिन्न प्रकार के हाइपरलिंक बना सकता हूँ?

उत्तर: हां, आप लिंक संरचना तत्वों का उपयोग करके विभिन्न प्रकार के हाइपरलिंक बना सकते हैं। .NET के लिए Aspose.PDF आपको सादे पाठ, समृद्ध पाठ, छवियों और बहु-पंक्ति विवरण के साथ हाइपरलिंक बनाने की अनुमति देता है, जो दस्तावेज़ के भीतर बाहरी सामग्री या स्थानों से लिंक करने के तरीके में बहुमुखी प्रतिभा प्रदान करता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में लिंक संरचना तत्वों को कैसे सेट अप और आरंभ करूँ?

 उत्तर: लिंक संरचना तत्वों का उपयोग करने के लिए, आपको सबसे पहले एक नया पीडीएफ दस्तावेज़ बनाना होगा`Document` वर्ग। फिर, टैग की गई सामग्री प्राप्त करें`TaggedContent`दस्तावेज़ की संपत्ति। वहां से, आप लिंक संरचना तत्वों को बना और अनुकूलित कर सकते हैं और उन्हें रूट संरचना तत्व में जोड़ सकते हैं।

#### प्रश्न: मैं लिंक संरचना तत्वों का उपयोग करके एक सरल पाठ हाइपरलिंक कैसे बना सकता हूं?
 उत्तर: आप एक सरल टेक्स्ट हाइपरलिंक बनाकर बना सकते हैं`LinkElement` और इसकी स्थापना`Hyperlink` संपत्ति को एक`WebHyperlink` उस URL के साथ जिसे आप लिंक करना चाहते हैं। आप लिंक का डिस्प्ले टेक्स्ट भी सेट कर सकते हैं`SetText` तरीका।

#### प्रश्न: क्या लिंक संरचना तत्वों का उपयोग करके छवियों के साथ हाइपरलिंक बनाना संभव है?

 उत्तर: हां, आप लिंक संरचना तत्वों का उपयोग करके छवियों के साथ हाइपरलिंक बना सकते हैं। आप एक हाइपरलिंक बनाएंगे`LinkElement` और फिर जोड़ें`FigureElement` इसमें एक छवि भी शामिल है। यह आपको एक छवि-आधारित हाइपरलिंक बनाने की अनुमति देता है।

#### प्रश्न: मैं यह कैसे सुनिश्चित कर सकता हूं कि हाइपरलिंक वाला मेरा पीडीएफ दस्तावेज़ पहुंच-योग्यता के लिए पीडीएफ/यूए मानक के अनुरूप है?

 उत्तर: .NET के लिए Aspose.PDF आपके PDF दस्तावेज़ के PDF/UA मानक के साथ अनुपालन को सत्यापित करने की क्षमता प्रदान करता है।`Validate` की विधि`Document`यह सुनिश्चित करता है कि दस्तावेज़ के हाइपरलिंक विकलांग उपयोगकर्ताओं के लिए सुलभ हैं।

#### प्रश्न: लिंक संरचना तत्वों के लिए वैकल्पिक विवरण क्या हैं, और वे महत्वपूर्ण क्यों हैं?

उत्तर: लिंक संरचना तत्वों के लिए वैकल्पिक विवरण (alt text) हाइपरलिंक्स का पाठ्य विवरण प्रदान करते हैं। ये विवरण पहुँच के लिए आवश्यक हैं, जिससे दृष्टिबाधित उपयोगकर्ता लिंक के उद्देश्य और उसके गंतव्य को समझ सकें।

#### प्रश्न: क्या मैं लिंक संरचना तत्वों का उपयोग करके बनाए गए हाइपरलिंक्स के स्वरूप और व्यवहार को अनुकूलित कर सकता हूं?

उत्तर: जबकि लिंक संरचना तत्व मुख्य रूप से हाइपरलिंक बनाने पर ध्यान केंद्रित करते हैं, आप .NET के लिए Aspose.PDF द्वारा प्रदान की गई अन्य सुविधाओं का उपयोग करके हाइपरलिंक की उपस्थिति और व्यवहार को और भी अनुकूलित कर सकते हैं। इसमें रंग, शैलियाँ और लिंक क्रियाएँ निर्दिष्ट करना शामिल है।

#### प्रश्न: लिंक संरचना तत्व पीडीएफ दस्तावेजों को अधिक इंटरैक्टिव और उपयोगकर्ता-अनुकूल बनाने में कैसे योगदान देते हैं?

उत्तर: लिंक संरचना तत्व स्थिर पीडीएफ दस्तावेजों को क्लिक करने योग्य हाइपरलिंक जोड़कर इंटरैक्टिव अनुभवों में बदल देते हैं। यह अन्तरक्रियाशीलता उपयोगकर्ता की सहभागिता को बेहतर बनाती है, संबंधित सामग्री के बीच सहज नेविगेशन को सक्षम बनाती है, और दस्तावेज़ की समग्र उपयोगिता को बढ़ाती है।