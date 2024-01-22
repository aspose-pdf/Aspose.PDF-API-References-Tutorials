---
title: पीडीएफ फाइल में हाइपरलिंक जोड़ें
linktitle: पीडीएफ फाइल में हाइपरलिंक जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ आसानी से PDF फ़ाइल में इंटरैक्टिव हाइपरलिंक जोड़ें।
type: docs
weight: 10
url: /hi/net/programming-with-links-and-actions/add-hyperlink/
---
पीडीएफ फ़ाइल में हाइपरलिंक जोड़ने से आप दस्तावेज़ में अन्य पृष्ठों, वेबसाइटों या गंतव्यों के लिए इंटरैक्टिव हाइपरलिंक बना सकते हैं। .NET के लिए Aspose.PDF के साथ, आप निम्नलिखित स्रोत कोड का पालन करके आसानी से हाइपरलिंक जोड़ सकते हैं:

## चरण 1: आवश्यक पुस्तकालय आयात करें

शुरू करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करनी होगी। यहाँ आवश्यक आयात निर्देश है:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## चरण 2: दस्तावेज़ फ़ोल्डर में पथ सेट करें

इस चरण में, आपको उस पीडीएफ फ़ाइल वाले फ़ोल्डर का पथ निर्दिष्ट करना होगा जिसमें आप हाइपरलिंक जोड़ना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"`आपके दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 3: पीडीएफ दस्तावेज़ खोलें

अब हम पीडीएफ दस्तावेज़ खोलेंगे जिसमें हम निम्नलिखित कोड का उपयोग करके एक हाइपरलिंक जोड़ना चाहते हैं:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## चरण 4: एक लिंक बनाएं

 इस चरण में, हम इसका उपयोग करके एक हाइपरलिंक बनाएंगे`LinkAnnotation` टिप्पणी. हम संपर्क विवरण और लिंक का क्षेत्र, लिंक का प्रकार और लिंक की सामग्री निर्दिष्ट करेंगे। यहाँ संबंधित कोड है:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## चरण 5: अतिरिक्त पाठ जोड़ें

 हाइपरलिंक के अलावा, हम इसका उपयोग करके अतिरिक्त टेक्स्ट भी जोड़ सकते हैं`FreeTextAnnotation` टिप्पणी. हम निर्देशांक, पाठ स्वरूप और पाठ सामग्री निर्दिष्ट करेंगे। यहाँ संबंधित कोड है:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## चरण 6: अद्यतन फ़ाइल सहेजें

 अब अपडेटेड पीडीएफ फाइल को इसका उपयोग करके सेव करें`Save` की विधि`document` वस्तु। यहाँ संबंधित कोड है:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके हाइपरलिंक जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document document = new Document(dataDir + "AddHyperlink.pdf");
// लिंक बनाएं
Page page = document.Pages[1];
// लिंक एनोटेशन ऑब्जेक्ट बनाएं
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// LinkAnnotation के लिए बॉर्डर ऑब्जेक्ट बनाएं
Border border = new Border(link);
// सीमा चौड़ाई मान को 0 पर सेट करें
border.Width = 0;
// LinkAnnotation के लिए बॉर्डर सेट करें
link.Border = border;
// लिंक प्रकार को दूरस्थ यूआरआई के रूप में निर्दिष्ट करें
link.Action = new GoToURIAction("www.aspose.com");
//पीडीएफ फ़ाइल के पहले पृष्ठ के एनोटेशन संग्रह में लिंक एनोटेशन जोड़ें
page.Annotations.Add(link);
// निःशुल्क टेक्स्ट एनोटेशन बनाएं
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// निःशुल्क पाठ के रूप में जोड़ी जाने वाली स्ट्रिंग
textAnnotation.Contents = "Link to Aspose website";
// निःशुल्क टेक्स्ट एनोटेशन के लिए बॉर्डर सेट करें
textAnnotation.Border = border;
// दस्तावेज़ के पहले पृष्ठ के एनोटेशन संग्रह में फ्रीटेक्स्ट एनोटेशन जोड़ें
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// अद्यतन दस्तावेज़ सहेजें
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## निष्कर्ष

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF के साथ हाइपरलिंक जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका है। आप अपने पीडीएफ दस्तावेज़ों में इंटरैक्टिव लिंक बनाने के लिए इस कोड का उपयोग कर सकते हैं।

### पीडीएफ फ़ाइल में हाइपरलिंक जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मुझे अपनी पीडीएफ फाइलों में हाइपरलिंक जोड़ने पर विचार क्यों करना चाहिए?

उ: अपनी पीडीएफ फाइलों में हाइपरलिंक जोड़ने से पाठकों को दस्तावेज़ के भीतर अन्य पृष्ठों, वेबसाइटों या गंतव्यों पर आसानी से नेविगेट करने की अनुमति देकर उपयोगकर्ता अनुभव बढ़ता है। यह अतिरिक्त संसाधनों या संबंधित जानकारी तक पहुंचने का एक निर्बाध तरीका प्रदान करता है।

#### प्रश्न: क्या .NET के लिए Aspose.PDF शुरुआती लोगों के लिए उपयुक्त है?

उत्तर: हां, .NET के लिए Aspose.PDF शुरुआती-अनुकूल है। इस गाइड में प्रदान किया गया चरण-दर-चरण ट्यूटोरियल पीडीएफ फाइलों में हाइपरलिंक जोड़ने की प्रक्रिया को सरल बनाता है, जिससे यह विभिन्न कौशल स्तरों के डेवलपर्स के लिए सुलभ हो जाता है।

#### प्रश्न: क्या मैं हाइपरलिंक्स के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: बिल्कुल! .NET के लिए Aspose.PDF टेक्स्ट रंग, शैली और फ़ॉर्मेटिंग सहित हाइपरलिंक उपस्थिति के लिए अनुकूलन विकल्प प्रदान करता है। यह आपको हाइपरलिंक को अपने दस्तावेज़ के समग्र डिज़ाइन से मिलान करने की अनुमति देता है।

#### प्रश्न: क्या हाइपरलिंक सभी प्रकार के पीडीएफ दस्तावेज़ों में समर्थित हैं?

उत्तर: हां, हाइपरलिंक को विभिन्न प्रकार के पीडीएफ दस्तावेज़ों में जोड़ा जा सकता है, जिनमें टेक्स्ट-आधारित दस्तावेज़, चित्र और मल्टीमीडिया-समृद्ध फ़ाइलें शामिल हैं। .NET के लिए Aspose.PDF यह सुनिश्चित करता है कि हाइपरलिंक विभिन्न पीडीएफ प्रारूपों में कार्यात्मक हैं।

#### प्रश्न: .NET के लिए Aspose.PDF कौन सी अन्य कार्यक्षमताएँ प्रदान करता है?

उ: .NET के लिए Aspose.PDF एक मजबूत लाइब्रेरी है जो पीडीएफ पीढ़ी, हेरफेर, रूपांतरण और निष्कर्षण सहित सुविधाओं की एक विस्तृत श्रृंखला प्रदान करती है। यह टेक्स्ट, छवियों, एनोटेशन और बहुत कुछ के साथ काम करने का समर्थन करता है, जिससे यह पीडीएफ-संबंधित कार्यों के लिए एक बहुमुखी उपकरण बन जाता है।

#### प्रश्न: क्या दस्तावेज़ के विशिष्ट अनुभागों में हाइपरलिंक जोड़े जा सकते हैं?

 उत्तर: हाँ, का उपयोग कर रहा हूँ`LinkAnnotation` एनोटेशन, आप हाइपरलिंक बना सकते हैं जो उपयोगकर्ताओं को पीडीएफ दस्तावेज़ के भीतर विशिष्ट अनुभागों तक निर्देशित करते हैं। यह सुविधा सामग्री या संदर्भ लिंक की इंटरैक्टिव तालिका बनाने के लिए विशेष रूप से उपयोगी है।

#### प्रश्न: क्या पीडीएफ फाइलों में हाइपरलिंक जोड़ने की कोई सीमाएँ हैं?

उत्तर: जबकि .NET के लिए Aspose.PDF व्यापक हाइपरलिंक कार्यक्षमता प्रदान करता है, यह सुनिश्चित करना महत्वपूर्ण है कि लिंक की गई सामग्री पहुंच योग्य और अद्यतित रहे। टूटे हुए लिंक से बचने के लिए बाहरी वेबसाइटों के हाइपरलिंक को नियमित रूप से सत्यापित किया जाना चाहिए।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके बाहरी फ़ाइलों के लिए हाइपरलिंक बना सकता हूँ?

उत्तर: हां, वेब यूआरएल के अलावा, आप हाइपरलिंक बना सकते हैं जो बाहरी फ़ाइलों, जैसे अन्य पीडीएफ दस्तावेज़, चित्र या मल्टीमीडिया फ़ाइलों तक ले जाते हैं। .NET के लिए Aspose.PDF विभिन्न प्रकार के संसाधनों से लिंक करने की सुविधा प्रदान करता है।