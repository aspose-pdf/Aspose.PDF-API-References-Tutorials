---
title: पीडीएफ फाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ें
linktitle: पीडीएफ फाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छायांकित रंगों के साथ पाठ जोड़ने का तरीका जानें।
type: docs
weight: 80
url: /hi/net/programming-with-text/add-text-with-shading-colors/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप छायांकित रंगों के साथ पाठ जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: पीडीएफ दस्तावेज़ लोड करें
 मौजूदा PDF दस्तावेज़ को लोड करें`Document` कंस्ट्रक्टर और दस्तावेज़ फ़ाइल के लिए पथ प्रदान करें।

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // कोड यहाँ है...
}
```

## चरण 5: संशोधित करने के लिए पाठ ढूंढें
उपयोग`TextFragmentAbsorber` दस्तावेज़ के भीतर वांछित पाठ खोजने के लिए। प्रदान किए गए कोड में, यह "Lorem ipsum" पाठ की तलाश करता है।

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## चरण 6: पाठ के लिए छायांकन रंग सेट करें
 एक नया बनाएँ`Color` पैटर्न कलरस्पेस के साथ ऑब्जेक्ट और ग्रेडिएंट शेडिंग रंग निर्दिष्ट करें। इस रंग को असाइन करें`ForegroundColor` की संपत्ति`TextState` की`TextFragment` वस्तु।

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## चरण 7: अतिरिक्त पाठ स्वरूपण लागू करें (वैकल्पिक)
 आप पाठ खंड पर अतिरिक्त स्वरूपण लागू कर सकते हैं, जैसे रेखांकन, इसके गुणों को संशोधित करके`TextState` वस्तु।

```csharp
textFragment.TextState.Underline = true;
```

## चरण 8: संशोधित PDF दस्तावेज़ को सहेजें
 संशोधित PDF दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके शेडिंग रंगों के साथ टेक्स्ट जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// पैटर्न कलरस्पेस के साथ नया रंग बनाएं
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके अपने PDF दस्तावेज़ में शेडिंग रंगों के साथ सफलतापूर्वक टेक्स्ट जोड़ लिया है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का मुख्य फोकस क्या है?

उत्तर: यह ट्यूटोरियल आपको .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ने की प्रक्रिया के बारे में बताता है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने होंगे?

उत्तर: उस कोड फ़ाइल में जहाँ आप छायांकित रंगों के साथ पाठ जोड़ना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं मौजूदा पीडीएफ दस्तावेज़ कैसे लोड करूं?

 उत्तर: चरण 4 में, आप एक मौजूदा पीडीएफ दस्तावेज़ को लोड करेंगे`Document` कंस्ट्रक्टर और दस्तावेज़ फ़ाइल का पथ प्रदान करना:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // कोड यहाँ है...
}
```

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में विशिष्ट पाठ कैसे ढूंढूं और संशोधित करूं?

 उत्तर: चरण 5 में, आप इसका उपयोग करेंगे`TextFragmentAbsorber` दस्तावेज़ में वांछित पाठ ढूँढ़ने के लिए। फिर, आप इसके गुणों को संशोधित कर सकते हैं:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### प्रश्न: मैं पाठ के लिए छायांकन रंग कैसे निर्धारित कर सकता हूँ?

 उत्तर: चरण 6 में, आप एक नया बनाएंगे`Color` पैटर्न कलरस्पेस के साथ ऑब्जेक्ट और ग्रेडिएंट शेडिंग रंग निर्दिष्ट करें। इस रंग को असाइन करें`ForegroundColor` की संपत्ति`TextState` की`TextFragment` वस्तु:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### प्रश्न: क्या मैं संशोधित पाठ पर अतिरिक्त पाठ स्वरूपण लागू कर सकता हूँ?

उत्तर: हां, चरण 7 में, आप गुणों को संशोधित करके अतिरिक्त पाठ स्वरूपण जैसे रेखांकन लागू कर सकते हैं।`TextState` वस्तु:

```csharp
textFragment.TextState.Underline = true;
```

#### प्रश्न: मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: चरण 8 में, आप संशोधित PDF दस्तावेज़ को निम्न का उपयोग करके सहेजेंगे:`Save` की विधि`Document` वस्तु:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके शेडिंग रंगों के साथ टेक्स्ट जोड़कर अपने PDF दस्तावेज़ को कैसे बेहतर बनाया जाए। यह आपकी PDF फ़ाइलों के भीतर विशिष्ट टेक्स्ट सामग्री को हाइलाइट करने और उस पर ज़ोर देने के लिए विशेष रूप से उपयोगी हो सकता है।