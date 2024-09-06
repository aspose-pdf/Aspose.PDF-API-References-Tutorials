---
title: पीडीएफ फाइल में फ्लोटिंग बॉक्स सामग्री के लिए पाठ संरेखण
linktitle: पीडीएफ फाइल में फ्लोटिंग बॉक्स सामग्री के लिए पाठ संरेखण
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में फ्लोटिंग बॉक्स के भीतर टेक्स्ट को संरेखित करना सीखें।
type: docs
weight: 520
url: /hi/net/programming-with-text/text-alignment-for-floating-box-contents/
---
यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में फ़्लोटिंग बॉक्स के भीतर टेक्स्ट को कैसे संरेखित किया जाए। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

## आवश्यक शर्तें

ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित है। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या अपने प्रोजेक्ट में इसे स्थापित करने के लिए NuGet का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें

अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाकर आरंभ करें और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें

आवश्यक नामस्थानों को आयात करने के लिए अपनी C# फ़ाइल के आरंभ में निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका का पथ सेट करें

 का उपयोग करके अपने दस्तावेज़ निर्देशिका का पथ सेट करें`dataDir` चर:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 4: नया दस्तावेज़ बनाएँ

 एक नया बनाएँ`Document` वस्तु:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## चरण 5: टेक्स्ट फ़्रैगमेंट के साथ फ़्लोटिंग बॉक्स बनाएँ

 एकाधिक बनाएँ`FloatingBox` विभिन्न ऊर्ध्वाधर संरेखण और क्षैतिज संरेखण वाली वस्तुएं:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 पाठ और शैली को संशोधित करें`TextFragment` इच्छानुसार वस्तुओं का प्रयोग करें।

## चरण 6: पीडीएफ दस्तावेज़ सहेजें

संशोधित PDF दस्तावेज़ सहेजें:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"FloatingBox_alignment_review_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ.

### .NET के लिए Aspose.PDF का उपयोग करके फ्लोटिंग बॉक्स सामग्री के लिए पाठ संरेखण के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में फ़्लोटिंग बॉक्स के भीतर टेक्स्ट को कैसे संरेखित किया जाए। इस ट्यूटोरियल में प्रोजेक्ट को सेट अप करने से लेकर संशोधित दस्तावेज़ को सहेजने तक, चरण-दर-चरण मार्गदर्शिका प्रदान की गई है। अब आप PDF फ़ाइलों में फ़्लोटिंग बॉक्स के भीतर टेक्स्ट के संरेखण को अनुकूलित करने के लिए इस कोड को अपने स्वयं के C# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में फ्लोटिंग बॉक्स सामग्री के लिए टेक्स्ट संरेखण" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में फ्लोटिंग बॉक्स कंटेंट के लिए टेक्स्ट अलाइनमेंट" ट्यूटोरियल का उद्देश्य उपयोगकर्ताओं को यह बताना है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में फ्लोटिंग बॉक्स के भीतर टेक्स्ट को कैसे अलाइन किया जाए। ट्यूटोरियल प्रक्रिया को प्रदर्शित करने के लिए चरण-दर-चरण निर्देश और C# कोड नमूने प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल फ्लोटिंग बॉक्स के भीतर टेक्स्ट संरेखित करने में कैसे मदद करता है?

उत्तर: यह ट्यूटोरियल उपयोगकर्ताओं को यह समझने में मदद करता है कि PDF दस्तावेज़ में फ़्लोटिंग बॉक्स के भीतर टेक्स्ट को संरेखित करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। दिए गए चरणों और कोड उदाहरणों का पालन करके, उपयोगकर्ता फ़्लोटिंग बॉक्स के भीतर टेक्स्ट के ऊर्ध्वाधर और क्षैतिज संरेखण को अनुकूलित कर सकते हैं।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए क्या पूर्वापेक्षाएँ आवश्यक हैं?

उत्तर: ट्यूटोरियल शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपके पास .NET लाइब्रेरी के लिए Aspose.PDF स्थापित होना चाहिए। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या NuGet का उपयोग करके अपने प्रोजेक्ट में इंस्टॉल कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उत्तर: आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया C# प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। यह आपको PDF दस्तावेज़ों के साथ काम करने और फ़्लोटिंग बॉक्स के भीतर टेक्स्ट संरेखित करने के लिए लाइब्रेरी की सुविधाओं का लाभ उठाने में सक्षम बनाता है।

#### प्रश्न: क्या मैं किसी भी प्रकार के फ्लोटिंग बॉक्स में टेक्स्ट संरेखित करने के लिए इस ट्यूटोरियल का उपयोग कर सकता हूँ?

उत्तर: हाँ, यह ट्यूटोरियल .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में फ़्लोटिंग बॉक्स के भीतर टेक्स्ट को संरेखित करने के तरीके के बारे में निर्देश प्रदान करता है। आप फ़्लोटिंग बॉक्स के भीतर टेक्स्ट के ऊर्ध्वाधर और क्षैतिज संरेखण को अनुकूलित करने के लिए दिए गए कोड नमूनों का उपयोग कर सकते हैं।

#### प्रश्न: मैं फ्लोटिंग बॉक्स में पाठ का संरेखण कैसे निर्दिष्ट करूं?

 उत्तर: ट्यूटोरियल दर्शाता है कि कैसे बनाएं`FloatingBox`वस्तुओं और उनके सेट`VerticalAlignment` और`HorizontalAlignment` निहित पाठ के संरेखण को नियंत्रित करने के लिए गुण। आप अपनी आवश्यकताओं के अनुसार इन गुणों को समायोजित कर सकते हैं।

#### प्रश्न: मैं फ्लोटिंग बक्सों के स्वरूप को कैसे अनुकूलित कर सकता हूं?

 उत्तर: आप फ़्लोटिंग बॉक्स की उपस्थिति को बॉर्डर, आकार और टेक्स्ट सामग्री जैसे गुणों को संशोधित करके अनुकूलित कर सकते हैं। ट्यूटोरियल कोड नमूने प्रदान करता है जो दर्शाता है कि कैसे बनाएं और स्टाइल करें`FloatingBox` वस्तुएं.

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ में अलग-अलग संरेखण वाले कई फ्लोटिंग बॉक्स जोड़ सकता हूं?

 उत्तर: हां, ट्यूटोरियल में बताया गया है कि एक से अधिक फाइलें कैसे बनाई जाती हैं।`FloatingBox` अलग-अलग ऊर्ध्वाधर और क्षैतिज संरेखण वाली वस्तुओं को एक ही पीडीएफ दस्तावेज़ में जोड़ें। यह आपको एक ही दस्तावेज़ में विभिन्न संरेखण के प्रभावों को देखने की अनुमति देता है।

#### प्रश्न: मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: संशोधित पीडीएफ दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document` यह ट्यूटोरियल कोड नमूने प्रदान करता है जो दर्शाता है कि परिणामी पीडीएफ दस्तावेज़ को कैसे सहेजना है।