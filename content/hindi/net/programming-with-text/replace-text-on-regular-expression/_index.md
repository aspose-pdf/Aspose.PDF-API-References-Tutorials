---
title: पीडीएफ फाइल में टेक्स्ट को रेगुलर एक्सप्रेशन से बदलें
linktitle: टेक्स्टन रेगुलर एक्सप्रेशन को पीडीएफ फाइल में बदलें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में रेगुलर एक्सप्रेशन के आधार पर टेक्स्ट को बदलने का तरीका जानें।
type: docs
weight: 360
url: /hi/net/programming-with-text/replace-text-on-regular-expression/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में रेगुलर एक्सप्रेशन के आधार पर टेक्स्ट को कैसे बदला जाए। हम आवश्यक C# स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित।
- C# प्रोग्रामिंग की बुनियादी समझ।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 उस निर्देशिका का पथ सेट करें जहां आपके पास इनपुट पीडीएफ फाइल है। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` आपकी पीडीएफ फाइल के पथ के साथ परिवर्तनीय।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ लोड करें

 का उपयोग करके पीडीएफ दस्तावेज़ लोड करें`Document` Aspose.PDF लाइब्रेरी से कक्षा।

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## चरण 3: रेगुलर एक्सप्रेशन का उपयोग करके टेक्स्ट खोजें और बदलें

 एक बनाने के`TextFragmentAbsorber` ऑब्जेक्ट करें और पैटर्न से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए नियमित अभिव्यक्ति पैटर्न निर्दिष्ट करें। नियमित अभिव्यक्ति उपयोग को सक्षम करने के लिए टेक्स्ट खोज विकल्प सेट करें।

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // जैसे 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## चरण 4: टेक्स्ट बदलें

निकाले गए टेक्स्ट अंशों के माध्यम से लूप करें और आवश्यकतानुसार टेक्स्ट को बदलें। टेक्स्ट और अन्य गुणों जैसे फ़ॉन्ट, फ़ॉन्ट आकार, अग्रभूमि रंग और पृष्ठभूमि रंग को अपडेट करें।

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## चरण 5: संशोधित पीडीएफ को सहेजें

संशोधित पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजें।

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्टॉन रेगुलर एक्सप्रेशन को बदलने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// रेगुलर एक्सप्रेशन से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए टेक्स्टएब्जॉर्बर ऑब्जेक्ट बनाएं
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // जैसे 1999-2000
// नियमित अभिव्यक्ति उपयोग निर्दिष्ट करने के लिए पाठ खोज विकल्प सेट करें
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// एक पृष्ठ के लिए अवशोषक स्वीकार करें
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// टुकड़ों के माध्यम से लूप करें
foreach (TextFragment textFragment in textFragmentCollection)
{
	// पाठ और अन्य गुण अद्यतन करें
	textFragment.Text = "New Phrase";
	// किसी ऑब्जेक्ट के उदाहरण पर सेट करें।
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में रेगुलर एक्सप्रेशन के आधार पर टेक्स्ट को कैसे बदला जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक पीडीएफ दस्तावेज़ लोड कर सकते हैं, नियमित अभिव्यक्ति का उपयोग करके टेक्स्ट खोज सकते हैं, इसे बदल सकते हैं, और संशोधित पीडीएफ को सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में रेगुलर एक्सप्रेशन पर टेक्स्ट बदलें" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में रेगुलर एक्सप्रेशन पर टेक्स्ट बदलें" ट्यूटोरियल का उद्देश्य रेगुलर एक्सप्रेशन के आधार पर पीडीएफ दस्तावेज़ में टेक्स्ट को खोजने और बदलने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करना है। यह नमूना C# कोड के साथ चरण-दर-चरण मार्गदर्शिका प्रदान करता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में टेक्स्ट को बदलने के लिए रेगुलर एक्सप्रेशन का उपयोग क्यों करना चाहूंगा?

उ: रेगुलर एक्सप्रेशन का उपयोग करने से आप एक विशिष्ट प्रारूप का पालन करने वाले टेक्स्ट पैटर्न को खोज और बदल सकते हैं, जिससे यह सामग्री में हेरफेर करने का एक शक्तिशाली तरीका बन जाता है। यह दृष्टिकोण विशेष रूप से तब उपयोगी होता है जब आपको पीडीएफ दस्तावेज़ में एक निश्चित पैटर्न या संरचना से मेल खाने वाले पाठ को बदलने की आवश्यकता होती है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे सेट करूँ?

उ: दस्तावेज़ निर्देशिका स्थापित करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका के पथ के साथ परिवर्तनीय जहां आपकी इनपुट पीडीएफ फ़ाइल स्थित है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में रेगुलर एक्सप्रेशन के आधार पर टेक्स्ट को कैसे बदलूं?

उत्तर: ट्यूटोरियल आपको निम्नलिखित चरणों के माध्यम से मार्गदर्शन करता है:

1.  का उपयोग करके पीडीएफ दस्तावेज़ लोड करें`Document` कक्षा।
2.  एक बनाने के`TextFragmentAbsorber` ऑब्जेक्ट करें और पैटर्न से मेल खाने वाले वाक्यांशों को खोजने के लिए नियमित अभिव्यक्ति पैटर्न निर्दिष्ट करें। नियमित अभिव्यक्ति उपयोग को सक्षम करने के लिए टेक्स्ट खोज विकल्प सेट करें।
3. निकाले गए टेक्स्ट अंशों के माध्यम से लूप करें और टेक्स्ट को बदलें। आवश्यकतानुसार अन्य गुणों जैसे फ़ॉन्ट, फ़ॉन्ट आकार, अग्रभूमि रंग और पृष्ठभूमि रंग को अपडेट करें।
4. संशोधित पीडीएफ दस्तावेज़ सहेजें।

#### प्रश्न: क्या मैं जटिल रेगुलर एक्सप्रेशन का उपयोग करके टेक्स्ट को बदल सकता हूँ?

उत्तर: हां, आप पीडीएफ दस्तावेज़ में टेक्स्ट के मिलान और प्रतिस्थापन के लिए जटिल नियमित अभिव्यक्तियों का उपयोग कर सकते हैं। नियमित अभिव्यक्तियाँ पाठ में विशिष्ट पैटर्न या संरचनाओं की पहचान करने का एक लचीला तरीका प्रदान करती हैं।

####  प्रश्न: इसका उद्देश्य क्या है?`TextSearchOptions` class in the tutorial?

 ए: द`TextSearchOptions`क्लास आपको पाठ खोज विकल्प निर्दिष्ट करने की अनुमति देता है, जैसे पाठ अंशों की खोज करते समय नियमित अभिव्यक्ति के उपयोग को सक्षम करना। ट्यूटोरियल में, इसका उपयोग रेगुलर एक्सप्रेशन मोड को सक्षम करने के लिए किया जाता है`TextFragmentAbsorber`.

#### प्रश्न: क्या पाठ को बदलने के लिए नियमित अभिव्यक्तियों का उपयोग करते समय फ़ॉन्ट प्रतिस्थापन वैकल्पिक है?

उ: हाँ, पाठ को बदलने के लिए नियमित अभिव्यक्तियों का उपयोग करते समय फ़ॉन्ट प्रतिस्थापन वैकल्पिक है। यदि आप कोई नया फ़ॉन्ट निर्दिष्ट नहीं करते हैं, तो पाठ मूल पाठ खंड के फ़ॉन्ट को बनाए रखेगा।

#### प्रश्न: मैं रेगुलर एक्सप्रेशन का उपयोग करके एकाधिक पृष्ठों में टेक्स्ट को कैसे बदल सकता हूँ?

उ: आप ट्यूटोरियल उदाहरण के समान, पीडीएफ दस्तावेज़ के सभी पृष्ठों को शामिल करने के लिए टेक्स्ट टुकड़ों के माध्यम से लूप को संशोधित कर सकते हैं। इस तरह, आप रेगुलर एक्सप्रेशन पैटर्न के आधार पर कई पेजों पर टेक्स्ट को बदल सकते हैं।

#### प्रश्न: प्रदत्त कोड को निष्पादित करने का अपेक्षित परिणाम क्या है?

उ: ट्यूटोरियल का अनुसरण करके और दिए गए C# कोड को चलाकर, आप पीडीएफ दस्तावेज़ में उस टेक्स्ट को बदल देंगे जो निर्दिष्ट नियमित अभिव्यक्ति पैटर्न से मेल खाता है। बदले गए टेक्स्ट में आपके द्वारा निर्दिष्ट गुण होंगे, जैसे फ़ॉन्ट, फ़ॉन्ट आकार, अग्रभूमि रंग और पृष्ठभूमि रंग।

#### प्रश्न: क्या मैं जटिल फ़ॉर्मेटिंग वाले टेक्स्ट को बदलने के लिए इस दृष्टिकोण का उपयोग कर सकता हूँ?

उ: हाँ, आप फ़ॉन्ट, फ़ॉन्ट आकार, अग्रभूमि रंग और पृष्ठभूमि रंग जैसे गुणों को अपडेट करके प्रतिस्थापित पाठ के स्वरूपण को अनुकूलित कर सकते हैं। यह आपको आवश्यकतानुसार फ़ॉर्मेटिंग को बनाए रखने या संशोधित करने की अनुमति देता है।