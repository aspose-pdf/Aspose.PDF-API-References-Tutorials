---
title: पीडीएफ फाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ें
linktitle: पीडीएफ फाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ने का तरीका जानें।
type: docs
weight: 80
url: /hi/net/programming-with-text/add-text-with-shading-colors/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप शेडिंग रंगों के साथ टेक्स्ट जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निर्देश का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: पीडीएफ दस्तावेज़ लोड करें
 का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ को लोड करें`Document` कन्स्ट्रक्टर और दस्तावेज़ फ़ाइल के लिए पथ प्रदान करें।

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // कोड यहाँ जाता है...
}
```

## चरण 5: संशोधित करने के लिए टेक्स्ट ढूंढें
 उपयोग`TextFragmentAbsorber` दस्तावेज़ के भीतर वांछित पाठ ढूँढने के लिए। दिए गए कोड में, यह "लोरेम इप्सम" टेक्स्ट ढूंढता है।

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## चरण 6: टेक्स्ट के लिए शेडिंग रंग सेट करें
 कोई नया बनाएं`Color` एक पैटर्न कलरस्पेस के साथ ऑब्जेक्ट और ग्रेडिएंट शेडिंग रंग निर्दिष्ट करें। इस रंग को असाइन करें`ForegroundColor` की संपत्ति`TextState` की`TextFragment` वस्तु।

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## चरण 7: अतिरिक्त टेक्स्ट फ़ॉर्मेटिंग लागू करें (वैकल्पिक)
 आप पाठ खंड के गुणों को संशोधित करके, अंडरलाइनिंग जैसे अतिरिक्त स्वरूपण लागू कर सकते हैं`TextState` वस्तु।

```csharp
textFragment.TextState.Underline = true;
```

## चरण 8: संशोधित पीडीएफ दस्तावेज़ को सहेजें
 का उपयोग करके संशोधित पीडीएफ दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

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
आपने .NET के लिए Aspose.PDF का उपयोग करके अपने PDF दस्तावेज़ में शेडिंग रंगों के साथ सफलतापूर्वक टेक्स्ट जोड़ा है। परिणामी पीडीएफ फाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का मुख्य फोकस क्या है?

उ: यह ट्यूटोरियल आपको .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फाइल में शेडिंग रंगों के साथ टेक्स्ट जोड़ने की प्रक्रिया में मार्गदर्शन करता है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को दर्शाता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने की आवश्यकता है?

उ: कोड फ़ाइल में जहां आप शेडिंग रंगों के साथ टेक्स्ट जोड़ना चाहते हैं, फ़ाइल की शुरुआत में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: कोड में, लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं मौजूदा पीडीएफ दस्तावेज़ कैसे लोड करूं?

 उ: चरण 4 में, आप इसका उपयोग करके एक मौजूदा पीडीएफ दस्तावेज़ लोड करेंगे`Document` कंस्ट्रक्टर और दस्तावेज़ फ़ाइल को पथ प्रदान करना:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // कोड यहाँ जाता है...
}
```

#### प्रश्न: मैं पीडीएफ दस्तावेज़ के भीतर विशिष्ट पाठ को कैसे ढूंढूं और संशोधित करूं?

 उत्तर: चरण 5 में, आप इसका उपयोग करेंगे`TextFragmentAbsorber`दस्तावेज़ के भीतर वांछित पाठ ढूँढने के लिए। फिर, आप इसके गुणों को संशोधित कर सकते हैं:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### प्रश्न: मैं टेक्स्ट के लिए शेडिंग रंग कैसे सेट कर सकता हूं?

 उ: चरण 6 में, आप एक नया बनाएंगे`Color` एक पैटर्न कलरस्पेस के साथ ऑब्जेक्ट और ग्रेडिएंट शेडिंग रंग निर्दिष्ट करें। इस रंग को असाइन करें`ForegroundColor` की संपत्ति`TextState` की`TextFragment` वस्तु:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### प्रश्न: क्या मैं संशोधित पाठ में अतिरिक्त पाठ स्वरूपण लागू कर सकता हूँ?

 उ: हां, चरण 7 में, आप अतिरिक्त टेक्स्ट फ़ॉर्मेटिंग लागू कर सकते हैं जैसे कि गुणों को संशोधित करके रेखांकित करना`TextState` वस्तु:

```csharp
textFragment.TextState.Underline = true;
```

#### प्रश्न: मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उ: चरण 8 में, आप इसका उपयोग करके संशोधित पीडीएफ दस्तावेज़ को सहेजेंगे`Save` की विधि`Document` वस्तु:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके शेडिंग रंगों के साथ टेक्स्ट जोड़कर अपने पीडीएफ दस्तावेज़ को कैसे बढ़ाया जाए। यह आपकी पीडीएफ फाइलों में विशिष्ट पाठ सामग्री को उजागर करने और जोर देने के लिए विशेष रूप से उपयोगी हो सकता है।