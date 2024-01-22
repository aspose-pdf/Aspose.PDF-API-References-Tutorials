---
title: पीडीएफ फाइल में टीओसी जोड़ें
linktitle: पीडीएफ फाइल में टीओसी जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में सामग्री तालिका जोड़ने का तरीका जानें। उदाहरण स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका। दस्तावेज़ नेविगेशन को बढ़ावा दें!
type: docs
weight: 40
url: /hi/net/programming-with-document/addtoc/
---
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि पीडीएफ दस्तावेज़ों में सामग्री की तालिका जोड़ने के लिए .NET के लिए Aspose.PDF की पीडीएफ फ़ाइल में ऐड टीओसी (सामग्री तालिका) सुविधा का उपयोग कैसे करें। हम चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे और इसे प्राप्त करने के लिए आवश्यक C# स्रोत कोड की व्याख्या करेंगे। इस ट्यूटोरियल के अंत तक, आप .NET के लिए Aspose.PDF का उपयोग करके सामग्री तालिका के साथ एक पीडीएफ दस्तावेज़ तैयार करने में सक्षम होंगे।


## चरण 1: मौजूदा पीडीएफ फाइल लोड करें

 आरंभ करने के लिए, हमें एक मौजूदा पीडीएफ फाइल लोड करनी होगी। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपकी पीडीएफ फाइल के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## चरण 2: सामग्री तालिका के लिए एक नया पृष्ठ बनाएं

हम विषय-सूची रखने के लिए एक नया पेज बनाएंगे। निम्नलिखित कोड अनुक्रमणिका 1 पर एक नया पृष्ठ सम्मिलित करता है:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## चरण 3: सामग्री तालिका की जानकारी को परिभाषित करें

इसके बाद, हमें सामग्री तालिका की जानकारी को परिभाषित करने की आवश्यकता है। हम विषय-सूची का शीर्षक और अन्य गुण निर्धारित करेंगे। निम्नलिखित कोड जोड़ें:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## चरण 4: टीओसी तत्व बनाएं

अब, हम विषय-सूची के तत्व बनाएंगे। इस ट्यूटोरियल में, हम अलग-अलग पेजों के अनुरूप चार टीओसी तत्व बनाएंगे। अपनी आवश्यकताओं के अनुसार निम्नलिखित कोड को संशोधित करें:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## चरण 5: अद्यतन दस्तावेज़ सहेजें

 अंत में, हमें संशोधित दस्तावेज़ को विषय-सूची के साथ सहेजना होगा। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` वांछित आउटपुट फ़ाइल पथ के साथ नीचे दिए गए कोड में:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ों में TOC जोड़ने के लिए उदाहरण स्रोत कोड

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// मौजूदा पीडीएफ फाइलों को लोड करें
Document doc = new Document(dataDir + "AddTOC.pdf");

// पीडीएफ फाइल के पहले पेज तक पहुंच प्राप्त करें
Page tocPage = doc.Pages.Insert(1);

// टीओसी जानकारी का प्रतिनिधित्व करने के लिए ऑब्जेक्ट बनाएं
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// TOC के लिए शीर्षक सेट करें
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//स्ट्रिंग ऑब्जेक्ट बनाएं जिनका उपयोग TOC तत्वों के रूप में किया जाएगा
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// हेडिंग ऑब्जेक्ट बनाएं
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// शीर्षक वस्तु के लिए गंतव्य पृष्ठ निर्दिष्ट करें
	heading2.DestinationPage = doc.Pages[i + 2];

	// गंतव्य पृष्ठ
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// गंतव्य समन्वय
	segment2.Text = titles[i];

	// टीओसी वाले पेज पर शीर्षक जोड़ें
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// अद्यतन दस्तावेज़ सहेजें
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ों में सामग्री तालिका (TOC) कैसे जोड़ा जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप सामग्री तालिका के साथ आसानी से एक पीडीएफ दस्तावेज़ तैयार कर सकते हैं। टीओसी दस्तावेज़ की उपयोगिता को बढ़ाता है, जिससे उपयोगकर्ताओं को विशिष्ट अनुभागों या पृष्ठों पर अधिक कुशलता से नेविगेट करने की अनुमति मिलती है। .NET के लिए Aspose.PDF, .NET अनुप्रयोगों में पीडीएफ फाइलों के साथ काम करने के लिए एक मजबूत और उपयोगकर्ता-अनुकूल समाधान प्रदान करता है, जो आपको आसानी से गतिशील और इंटरैक्टिव पीडीएफ दस्तावेज़ बनाने में सक्षम बनाता है।

### पीडीएफ फाइल में टीओसी जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उ: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में पीडीएफ फाइलों के साथ प्रभावी ढंग से काम करने की अनुमति देती है। यह पीडीएफ दस्तावेजों को प्रोग्रामेटिक रूप से बनाने, हेरफेर करने और प्रबंधित करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

#### प्रश्न: पीडीएफ दस्तावेज़ में विषय-सूची (टीओसी) जोड़ने का उद्देश्य क्या है?

उ: सामग्री तालिका (टीओसी) उपयोगकर्ताओं के लिए एक नेविगेशनल सहायता प्रदान करती है, जो उन्हें पीडीएफ दस्तावेज़ के भीतर विशिष्ट अनुभागों या पृष्ठों पर तुरंत जाने में सक्षम बनाती है। यह दस्तावेज़ की उपयोगिता और उपयोगकर्ता अनुभव को बेहतर बनाता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके किसी PDF दस्तावेज़ में विषय-सूची कैसे जोड़ूँ?

उ: .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में सामग्री की एक तालिका जोड़ने के लिए, आपको TOC को होल्ड करने के लिए एक नया पेज बनाना होगा, सामग्री की तालिका की जानकारी को परिभाषित करना होगा, और फिर TOC तत्वों को बनाना होगा जो विशिष्ट पृष्ठों के अनुरूप हों या दस्तावेज़ में अनुभाग.

#### प्रश्न: क्या मैं विषय-सूची के स्वरूप को अनुकूलित कर सकता हूँ?

उ: हां, आप टीओसी तत्वों के विभिन्न गुणों, जैसे फ़ॉन्ट आकार, फ़ॉन्ट शैली और संरेखण को सेट करके सामग्री तालिका की उपस्थिति को अनुकूलित कर सकते हैं। .NET के लिए Aspose.PDF आपके वांछित रूप और अनुभव से मेल खाने के लिए TOC को डिज़ाइन करने में लचीलापन प्रदान करता है।

#### प्रश्न: क्या .NET के लिए Aspose.PDF PDF दस्तावेज़ों में उन्नत सुविधाएँ जोड़ने के लिए उपयुक्त है?

उत्तर: बिल्कुल, .NET के लिए Aspose.PDF एक सुविधा संपन्न लाइब्रेरी है जो आपको इंटरैक्टिव तत्वों, फॉर्म फ़ील्ड, डिजिटल हस्ताक्षर और बहुत कुछ सहित पीडीएफ दस्तावेजों में उन्नत कार्यक्षमता जोड़ने की अनुमति देती है।