---
title: पीडीएफ फाइल में टेक्स्ट में टूलटिप जोड़ें
linktitle: पीडीएफ फाइल में टेक्स्ट में टूलटिप जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पाठ में टूलटिप्स जोड़ने का तरीका जानें।
type: docs
weight: 90
url: /hi/net/programming-with-text/add-tooltip-to-text/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट में टूलटिप्स जोड़ने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप टेक्स्ट में टूलटिप्स जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: पाठ के साथ एक नमूना दस्तावेज़ बनाएँ
 एक नया बनाएँ`Document` ऑब्जेक्ट और टेक्स्ट अंशों वाले पेज जोड़ें। दिए गए कोड में, संबंधित टूलटिप टेक्स्ट के साथ दस्तावेज़ में दो टेक्स्ट अंश जोड़े जाते हैं।

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## चरण 5: दस्तावेज़ खोलें और पाठ अंश ढूंढें
 निर्मित दस्तावेज़ को लोड करें`Document` कंस्ट्रक्टर का उपयोग करके उन टेक्स्ट अंशों को खोजें जिन्हें टूलटिप्स की आवश्यकता है`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## चरण 6: पाठ अंशों में टूलटिप्स जोड़ें
 निकाले गए टेक्स्ट अंशों के माध्यम से लूप करें और उनके स्थान पर अदृश्य बटन बनाएं। वांछित टूलटिप टेक्स्ट को असाइन करें`AlternateName` की संपत्ति`ButtonField`दस्तावेज़ के फ़ॉर्म में बटन फ़ील्ड जोड़ें.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## चरण 7: लंबे टूलटिप्स के साथ अतिरिक्त पाठ अंशों के लिए दोहराएं
लंबे टूलटिप वाले टेक्स्ट अंशों के लिए चरण 5 और 6 को दोहराएँ। खोज मानदंड और टूलटिप टेक्स्ट को तदनुसार संशोधित करें।

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## चरण 8: संशोधित दस्तावेज़ को सहेजें
 संशोधित PDF दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
document. Save(outputFile);
```

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट में टूलटिप जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// पाठ के साथ नमूना दस्तावेज़ बनाएँ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// पाठ सहित दस्तावेज़ खोलें
Document document = new Document(outputFile);
// नियमित अभिव्यक्ति से मेल खाने वाले सभी वाक्यांशों को खोजने के लिए TextAbsorber ऑब्जेक्ट बनाएं
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// दस्तावेज़ पृष्ठों के लिए अवशोषक स्वीकार करें
document.Pages.Accept(absorber);
// निकाले गए पाठ अंश प्राप्त करें
TextFragmentCollection textFragments = absorber.TextFragments;
// टुकड़ों के माध्यम से लूप
foreach (TextFragment fragment in textFragments)
{
	// पाठ खंड स्थिति पर अदृश्य बटन बनाएं
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// AlternateName मान को व्यूअर एप्लिकेशन द्वारा टूलटिप के रूप में प्रदर्शित किया जाएगा
	field.AlternateName = "Tooltip for text.";
	// दस्तावेज़ में बटन फ़ील्ड जोड़ें
	document.Form.Add(field);
}
// अगला बहुत लंबे टूलटिप का नमूना होगा
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// बहुत लंबा पाठ सेट करें
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// दस्तावेज़ सहेजें
document.Save(outputFile);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में टेक्स्ट में सफलतापूर्वक टूलटिप्स जोड़ दिए हैं। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

## पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

उत्तर: यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल के भीतर टेक्स्ट में टूलटिप्स जोड़ने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए कौन से नेमस्पेस को आयात करने की आवश्यकता है?

उत्तर: उस कोड फ़ाइल में जहां आप टेक्स्ट में टूलटिप्स जोड़ना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं पाठ के साथ एक नमूना दस्तावेज़ कैसे बना सकता हूँ?

 उत्तर: चरण 4 में, आप एक नया बनाएंगे`Document` ऑब्जेक्ट और टेक्स्ट अंशों वाले पेज जोड़ें। प्रदान किया गया कोड संबंधित टूलटिप टेक्स्ट के साथ दो टेक्स्ट अंश जोड़ता है।

#### प्रश्न: मैं दस्तावेज़ कैसे खोलूं और पाठ अंश कैसे ढूंढूं?

 उत्तर: चरण 5 में, आप बनाए गए दस्तावेज़ को का उपयोग करके लोड करेंगे`Document` कंस्ट्रक्टर का उपयोग करें और टूलटिप्स की आवश्यकता वाले टेक्स्ट अंशों को ढूंढें`TextFragmentAbsorber`.

#### प्रश्न: मैं पाठ अंशों में टूलटिप्स कैसे जोड़ूं?

 उत्तर: चरण 6 में, आप निकाले गए टेक्स्ट अंशों के माध्यम से लूप करेंगे और उनके स्थान पर अदृश्य बटन बनाएंगे। टूलटिप टेक्स्ट को असाइन किया गया है`AlternateName` की संपत्ति`ButtonField`जिसे दस्तावेज़ के फ़ॉर्म में जोड़ा जाता है.

#### प्रश्न: मैं लंबे टूलटिप्स वाले अतिरिक्त पाठ अंशों के लिए प्रक्रिया को कैसे दोहराऊं?

उत्तर: लंबे टूलटिप वाले पाठ अंशों के लिए, चरण 5 और 6 को दोहराएं। खोज मानदंड और टूलटिप पाठ को तदनुसार संशोधित करें।

#### प्रश्न: मैं संशोधित दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: चरण 8 में, आप संशोधित PDF दस्तावेज़ को निम्न का उपयोग करके सहेजेंगे:`Save` की विधि`Document` वस्तु।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट में टूलटिप्स जोड़कर अपने PDF दस्तावेज़ को कैसे बेहतर बनाया जाए। यह पाठकों को PDF सामग्री के साथ इंटरैक्ट करते समय मूल्यवान अतिरिक्त जानकारी प्रदान कर सकता है।