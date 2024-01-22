---
title: शब्दों को हटाओ
linktitle: शब्दों को हटाओ
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: यह आलेख .NET के स्ट्राइक आउट वर्ड्स फीचर के लिए Aspose.PDF का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करता है, जिसमें चरण-दर-चरण मार्गदर्शिका और स्पष्टीकरण शामिल हैं।
type: docs
weight: 150
url: /hi/net/annotations/strikeoutwords/
---
.NET के लिए Aspose.PDF एक पीडीएफ दस्तावेज़ हेरफेर और प्रसंस्करण लाइब्रेरी है जो पीडीएफ फाइलों को बनाने, संशोधित करने और परिवर्तित करने के लिए विभिन्न सुविधाएं प्रदान करता है। Aspose.PDF द्वारा प्रदान की जाने वाली उपयोगी सुविधाओं में से एक C# स्रोत कोड का उपयोग करके PDF दस्तावेज़ में शब्दों या वाक्यांशों को हटाने की क्षमता है। इस लेख में, हम .NET के लिए Aspose.PDF का उपयोग करके शब्दों को कैसे हटाएं, इस पर चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे।

## चरण 1: पीडीएफ दस्तावेज़ लोड हो रहा है
पहला कदम उस पीडीएफ दस्तावेज़ को लोड करना है जिसे आप संशोधित करना चाहते हैं। इस ट्यूटोरियल में, हम "आपके दस्तावेज़ निर्देशिका" फ़ोल्डर से "input.pdf" नामक एक पीडीएफ दस्तावेज़ लोड करेंगे। 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## चरण 2: पाठ के अंशों की खोज करना
पीडीएफ दस्तावेज़ में विशिष्ट शब्दों या वाक्यांशों को हटाने के लिए, आपको सबसे पहले उन्हें खोजना होगा। Aspose.PDF एक TextFragmentAbsorber वर्ग प्रदान करता है जिसका उपयोग PDF दस्तावेज़ में एक विशिष्ट पाठ खंड को खोजने के लिए किया जा सकता है।

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

उपरोक्त कोड में, हम पीडीएफ दस्तावेज़ में टेक्स्ट खंड "एस्टोक" की खोज कर रहे हैं। आप किसी अन्य शब्द या वाक्यांश को खोजने के लिए इसे संशोधित कर सकते हैं जिसे आप हटाना चाहते हैं।

## चरण 3: पाठ के अंशों को हटाना
पाठ के टुकड़े ढूंढने के बाद, अगला कदम उन्हें हटाना है। Aspose.PDF एक स्ट्राइकआउटएनोटेशन क्लास प्रदान करता है जिसका उपयोग टेक्स्ट खंड के लिए स्ट्राइक-आउट एनोटेशन बनाने के लिए किया जा सकता है। 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

उपरोक्त कोड में, हम पाए गए प्रत्येक पाठ खंड के लिए एक स्ट्राइक-आउट एनोटेशन बना रहे हैं। हम स्ट्राइक-आउट एनोटेशन की अपारदर्शिता, बॉर्डर और रंग भी सेट कर रहे हैं।

## चरण 4: संशोधित पीडीएफ दस्तावेज़ को सहेजना
पाठ के अंशों को हटाने के बाद, संशोधित दस्तावेज़ को सहेजें।

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके स्ट्राइक आउट वर्ड्स के लिए उदाहरण स्रोत कोड


```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document document = new Document(dataDir + "input.pdf");

// विशेष पाठ खंड को खोजने के लिए टेक्स्टफ्रैगमेंट अवशोषक उदाहरण बनाएं
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// पीडीएफ दस्तावेज़ के पृष्ठों के माध्यम से पुनरावृति करें
for (int i = 1; i <= document.Pages.Count; i++)
{
	// पीडीएफ दस्तावेज़ का पहला पृष्ठ प्राप्त करें
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// अवशोषित पाठ का एक संग्रह बनाएं
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//उपरोक्त संग्रह पर पुनरावृति करें
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// TextFragment ऑब्जेक्ट के आयताकार आयाम प्राप्त करें
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// त्वरित स्ट्राइकआउट एनोटेशन उदाहरण
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// एनोटेशन के लिए अपारदर्शिता सेट करें
	strikeOut.Opacity = .80f;
	// एनोटेशन उदाहरण के लिए बॉर्डर सेट करें
	strikeOut.Border = new Border(strikeOut);
	// एनोटेशन का रंग सेट करें
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// TextFragment के एनोटेशन संग्रह में एनोटेशन जोड़ें
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि पीडीएफ दस्तावेज़ में विशिष्ट शब्दों को हटाने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, आप आसानी से एक पीडीएफ दस्तावेज़ लोड कर सकते हैं, विशिष्ट पाठ अंशों की खोज कर सकते हैं, और उन शब्दों को दृष्टिगत रूप से चिह्नित करने और हटाने के लिए स्ट्राइक-आउट एनोटेशन बना सकते हैं। .NET के लिए Aspose.PDF प्रोग्रामेटिक रूप से PDF दस्तावेज़ों में हेरफेर करने का एक सरल और प्रभावी तरीका प्रदान करता है, जिससे यह .NET अनुप्रयोगों में PDF फ़ाइलों के साथ काम करने वाले डेवलपर्स के लिए एक मूल्यवान उपकरण बन जाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उत्तर: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, संपादित करने और हेरफेर करने की अनुमति देती है। यह पीडीएफ फाइलों के साथ काम करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें टेक्स्ट निष्कर्षण, एनोटेशन हैंडलिंग, फॉर्म भरना और बहुत कुछ शामिल है।

#### प्रश्न: क्या मैं PDF दस्तावेज़ में विशिष्ट शब्दों को हटाने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकता हूँ?

उत्तर: हां, .NET के लिए Aspose.PDF एक पीडीएफ दस्तावेज़ में विशिष्ट पाठ अंशों की खोज करने और फिर उन शब्दों को दृष्टिगत रूप से चिह्नित करने और हटाने के लिए स्ट्राइक-आउट एनोटेशन बनाने की कार्यक्षमता प्रदान करता है।

#### प्रश्न: मैं उस पाठ को कैसे निर्दिष्ट करूं जिसे मैं पीडीएफ दस्तावेज़ से हटाना चाहता हूं?

 उ: जिस पाठ को आप हटाना चाहते हैं उसे निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`TextFragmentAbsorber` .NET के लिए Aspose.PDF द्वारा प्रदान की गई कक्षा। यह आपको अपने वांछित मानदंडों के आधार पर पीडीएफ दस्तावेज़ में एक विशिष्ट पाठ खंड की खोज करने की अनुमति देता है।

#### प्रश्न: क्या मैं स्ट्राइक-आउट एनोटेशन के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हां, आप स्ट्राइक-आउट एनोटेशन के विभिन्न गुणों को अनुकूलित कर सकते हैं, जैसे अपारदर्शिता, बॉर्डर शैली और रंग। यह आपको स्ट्राइक-आउट एनोटेशन के स्वरूप को अपनी विशिष्ट आवश्यकताओं के अनुरूप बनाने की अनुमति देता है।