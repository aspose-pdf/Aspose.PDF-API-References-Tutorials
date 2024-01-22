---
title: पीडीएफ फाइल में परतें जोड़ें
linktitle: पीडीएफ फाइल में परतें जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइलों में परतें जोड़ने का तरीका जानें। स्तरित पीडीएफ बनाने और सहेजने के लिए कोड ट्यूटोरियल के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 20
url: /hi/net/programming-with-document/addlayers/
---
पीडीएफ फ़ाइल में परतें जोड़ने के लिए, हम .NET के लिए Aspose.PDF का उपयोग करेंगे। यह लाइब्रेरी हमें .NET अनुप्रयोगों में पीडीएफ फाइलों के साथ प्रभावी ढंग से काम करने की अनुमति देती है। .NET के लिए Aspose.PDF का उपयोग करके परतें जोड़ने के लिए नीचे दिए गए चरण-दर-चरण निर्देशों का पालन करें।

## चरण 1: एक नया पीडीएफ दस्तावेज़ बनाएं

 का एक नया उदाहरण बनाकर शुरुआत करें`Document` .NET के लिए Aspose.PDF द्वारा प्रदान की गई कक्षा। यह पीडीएफ दस्तावेज़ के रूप में काम करेगा जहां हम परतें जोड़ेंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## चरण 2: दस्तावेज़ में एक पृष्ठ जोड़ें

 इसके बाद, का उपयोग करके दस्तावेज़ में एक पृष्ठ जोड़ें`Add` की विधि`Pages` में संग्रह`Document` कक्षा।

```csharp
Page page = doc.Pages.Add();
```

## चरण 3: पृष्ठ पर परतें बनाएं और जोड़ें

 के उदाहरण बनाएँ`Layer` प्रत्येक परत के लिए क्लास जिसे आप पीडीएफ फाइल में जोड़ना चाहते हैं। प्रत्येक परत के लिए एक विशिष्ट पहचानकर्ता और एक नाम निर्दिष्ट करें।

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

इस ट्यूटोरियल में, हमने पेज पर अलग-अलग रंगों और नामों के साथ तीन परतें जोड़ी हैं।

## चरण 4: पीडीएफ फाइल को सेव करें

 का उपयोग करके संशोधित पीडीएफ फाइल को सेव करें`Save` की विधि`Document` कक्षा।

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

यह कोड संशोधित पीडीएफ फाइल को निर्दिष्ट निर्देशिका में सहेजेगा।

### .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ पेजों में परतें जोड़ने के लिए उदाहरण स्रोत कोड

```csharp            
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइलों में परतें जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान की है। निर्देशों का पालन करके और दिए गए कोड ट्यूटोरियल का उपयोग करके, आप आसानी से अपने पीडीएफ दस्तावेज़ों में परतें शामिल कर सकते हैं। परतें आपको सामग्री की दृश्यता को व्यवस्थित और नियंत्रित करने की अनुमति देती हैं, जो आपके उपयोगकर्ताओं के लिए अधिक इंटरैक्टिव और अनुकूलन योग्य अनुभव प्रदान करती हैं।


### पीडीएफ फ़ाइल में परतें जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उ: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में पीडीएफ फाइलों के साथ प्रभावी ढंग से काम करने में सक्षम बनाती है। यह पीडीएफ दस्तावेजों को बनाने, संशोधित करने और हेरफेर करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

#### प्रश्न: पीडीएफ परतें क्या हैं?

उ: पीडीएफ परतें, जिन्हें वैकल्पिक सामग्री समूह (ओसीजी) के रूप में भी जाना जाता है, आपको पीडीएफ फ़ाइल के भीतर विशिष्ट सामग्री की दृश्यता और उपस्थिति को नियंत्रित करने की अनुमति देती हैं। वे सामग्री को व्यवस्थित करने और इंटरैक्टिव दस्तावेज़ बनाने के लिए उपयोगी हैं।

#### प्रश्न: क्या मैं .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फाइल में कई परतें जोड़ सकता हूं?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फाइल में कई परतें जोड़ सकते हैं। जैसा कि ट्यूटोरियल में दिखाया गया है, प्रत्येक परत का अपना विशिष्ट पहचानकर्ता और नाम हो सकता है।

#### प्रश्न: मैं परतों के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

उ: आप रंग, अस्पष्टता और दृश्यता जैसे विभिन्न गुणों को निर्दिष्ट करके परतों की उपस्थिति को अनुकूलित कर सकते हैं। .NET के लिए Aspose.PDF इसे प्राप्त करने के लिए विभिन्न विकल्प प्रदान करता है।

#### प्रश्न: क्या .NET के लिए Aspose.PDF पेशेवर परियोजनाओं के लिए उपयुक्त है?

उत्तर: हां, .NET के लिए Aspose.PDF पेशेवर परियोजनाओं में पीडीएफ हेरफेर के लिए एक विश्वसनीय और व्यापक रूप से उपयोग की जाने वाली लाइब्रेरी है। यह .NET अनुप्रयोगों में पीडीएफ फाइलों के साथ काम करने के लिए व्यापक कार्यक्षमता और उत्कृष्ट प्रदर्शन प्रदान करता है।