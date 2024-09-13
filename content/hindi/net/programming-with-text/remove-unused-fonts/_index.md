---
title: पीडीएफ फाइल में अप्रयुक्त फ़ॉन्ट्स हटाएं
linktitle: पीडीएफ फाइल में अप्रयुक्त फ़ॉन्ट्स हटाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में अप्रयुक्त फ़ॉन्ट को हटाने का तरीका जानें।
type: docs
weight: 300
url: /hi/net/programming-with-text/remove-unused-fonts/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF फ़ाइल में अप्रयुक्त फ़ॉन्ट कैसे निकालें। हम PDF लोड करने, अप्रयुक्त फ़ॉन्ट की पहचान करने और हटाने, और दिए गए C# स्रोत कोड का उपयोग करके अपडेट किए गए PDF को सहेजने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आपकी पीडीएफ फाइलें स्थित हैं।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपनी पीडीएफ फाइलों के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत पीडीएफ लोड करें

 इसके बाद, हम स्रोत पीडीएफ दस्तावेज़ को लोड करते हैं`Document` Aspose.PDF लाइब्रेरी से क्लास.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## चरण 3: अप्रयुक्त फ़ॉन्ट्स की पहचान करें और उन्हें हटाएँ

 हम एक बनाते हैं`TextFragmentAbsorber` वस्तु के साथ`TextEditOptions` पैरामीटर सेट किया गया`TextEditOptions.FontReplace.RemoveUnusedFonts` यह विकल्प हमें पीडीएफ दस्तावेज़ में अप्रयुक्त फ़ॉन्ट की पहचान करने और उसे हटाने की अनुमति देता है। फिर हम सभी फ़ॉन्ट को फिर से दोहराते हैं।`TextFragments` और फ़ॉन्ट को इच्छित फ़ॉन्ट पर सेट करें.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## चरण 4: अपडेट की गई पीडीएफ को सेव करें

अंत में, हम अद्यतन किए गए पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके अप्रयुक्त फ़ॉन्ट्स को हटाने के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// स्रोत पीडीएफ फ़ाइल लोड करें
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// सभी टेक्स्ट फ़्रैगमेंट को दोहराएँ
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// अद्यतन दस्तावेज़ सहेजें
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ से अप्रयुक्त फ़ॉन्ट कैसे निकालें। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक PDF लोड कर सकते हैं, अप्रयुक्त फ़ॉन्ट की पहचान कर सकते हैं और उन्हें हटा सकते हैं, और अपडेट किए गए PDF को सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में अप्रयुक्त फ़ॉन्ट्स हटाएं" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में अप्रयुक्त फ़ॉन्ट निकालें" ट्यूटोरियल बताता है कि पीडीएफ दस्तावेज़ से अप्रयुक्त फ़ॉन्ट हटाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल आपको पीडीएफ लोड करने, अप्रयुक्त फ़ॉन्ट की पहचान करने और हटाने और अपडेट किए गए पीडीएफ को सहेजने की प्रक्रिया के माध्यम से मार्गदर्शन करता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ से अप्रयुक्त फ़ॉन्ट क्यों हटाना चाहूंगा?

उत्तर: PDF दस्तावेज़ से अप्रयुक्त फ़ॉन्ट हटाने से फ़ाइल का आकार कम करने और बेहतर प्रदर्शन के लिए दस्तावेज़ को अनुकूलित करने में मदद मिल सकती है। यह विशेष रूप से उपयोगी है जब PDF से निपटने की बात आती है जिसमें एम्बेडेड फ़ॉन्ट होते हैं जो वास्तव में दस्तावेज़ की सामग्री में उपयोग नहीं किए जाते हैं।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे स्थापित करूँ?

उत्तर: दस्तावेज़ निर्देशिका सेट अप करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` चर को उस निर्देशिका के पथ के साथ जोड़ें जहां आपकी पीडीएफ फाइलें स्थित हैं।

#### प्रश्न: मैं Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ से अप्रयुक्त फ़ॉन्ट कैसे हटा सकता हूँ?

उत्तर: ट्यूटोरियल आपको चरण दर चरण प्रक्रिया के माध्यम से मार्गदर्शन करता है:

1.  पीडीएफ दस्तावेज़ को खोलें`Document` कक्षा।
2.  एक बनाने के`TextFragmentAbsorber` वस्तु के साथ`TextEditOptions` करने के लिए सेट`FontReplace.RemoveUnusedFonts`.
3. पीडीएफ से अप्रयुक्त फ़ॉन्ट्स को पहचानने और हटाने के लिए अवशोषक को स्वीकार करें।
4.  सभी के माध्यम से पुनरावृति करें`TextFragments` और फ़ॉन्ट को इच्छित फ़ॉन्ट पर सेट करें.
5. अद्यतनित पीडीएफ दस्तावेज़ को सहेजें.

####  प्रश्न: इसका उद्देश्य क्या है?`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 उत्तर:`TextEditOptions.FontReplace.RemoveUnusedFonts` पैरामीटर निर्देश देता है`TextFragmentAbsorber`पीडीएफ दस्तावेज़ से अप्रयुक्त फ़ॉन्ट्स को पहचानने और हटाने के लिए।

#### प्रश्न: क्या मैं अप्रयुक्त फ़ॉन्ट को अपनी पसंद के फ़ॉन्ट से बदल सकता हूँ?

उत्तर: हां, आप अप्रयुक्त फ़ॉन्ट को अपनी पसंद के फ़ॉन्ट से बदलने के लिए कोड को संशोधित कर सकते हैं। दिए गए नमूना कोड में, फ़ॉन्ट "Arial, Bold" को प्रतिस्थापन के रूप में उपयोग किया जाता है।

#### प्रश्न:`TextFragmentAbsorber` work to remove unused fonts?

 उत्तर:`TextFragmentAbsorber` के साथ कॉन्फ़िगर किया गया है`TextEditOptions.FontReplace.RemoveUnusedFonts` पैरामीटर, जो पीडीएफ के टेक्स्ट अंशों में अप्रयुक्त फ़ॉन्ट की पहचान करता है। अवशोषण के बाद, आप इसके माध्यम से पुनरावृति कर सकते हैं`TextFragments` और अपने फ़ॉन्ट को वांछित प्रतिस्थापन फ़ॉन्ट पर सेट करें।

#### प्रश्न: दिए गए कोड को निष्पादित करने का अपेक्षित परिणाम क्या है?

उत्तर: ट्यूटोरियल का पालन करके और दिए गए C# कोड को चलाकर, आप इनपुट PDF दस्तावेज़ से अप्रयुक्त फ़ॉन्ट्स को हटा देंगे और अपडेट किए गए संस्करण को आउटपुट PDF फ़ाइल के रूप में सहेज लेंगे।

#### प्रश्न: क्या मैं केवल विशिष्ट पृष्ठों या क्षेत्रों से फ़ॉन्ट हटाने के लिए कोड को संशोधित कर सकता हूँ?

उत्तर: प्रदान किया गया कोड पूरे PDF दस्तावेज़ से अप्रयुक्त फ़ॉन्ट को हटाने पर केंद्रित है। यदि आप फ़ॉन्ट हटाने के लिए विशिष्ट पृष्ठों या क्षेत्रों को लक्षित करना चाहते हैं, तो आपको दृष्टिकोण को संशोधित करने और उन क्षेत्रों में अप्रयुक्त फ़ॉन्ट की पहचान करने के लिए अधिक जटिल तर्क का उपयोग करने की आवश्यकता होगी।