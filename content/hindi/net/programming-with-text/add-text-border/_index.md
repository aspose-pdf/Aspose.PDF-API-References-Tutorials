---
title: पीडीएफ फाइल में टेक्स्ट बॉर्डर जोड़ें
linktitle: पीडीएफ फाइल में टेक्स्ट बॉर्डर जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट बॉर्डर जोड़ने का तरीका जानें।
type: docs
weight: 70
url: /hi/net/programming-with-text/add-text-border/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में टेक्स्ट बॉर्डर जोड़ने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप टेक्स्ट बॉर्डर जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निर्देश का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: एक नया दस्तावेज़ ऑब्जेक्ट बनाएं
 एक नया त्वरित करें`Document` कोड की निम्नलिखित पंक्ति जोड़कर ऑब्जेक्ट करें:

```csharp
Document pdfDocument = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 का उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ें`Add` की विधि`Pages`संग्रह। दिए गए कोड में, नया पेज वेरिएबल को सौंपा गया है`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## चरण 6: एक टेक्स्टफ़्रैगमेंट बनाएं
 एक बनाने के`TextFragment` ऑब्जेक्ट करें और वांछित पाठ प्रदान करें। का उपयोग करके पाठ खंड की स्थिति निर्धारित करें`Position` संपत्ति। दिए गए कोड में, टेक्स्ट को "मुख्य टेक्स्ट" पर सेट किया गया है और पृष्ठ पर (100, 600) पर स्थित किया गया है।

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## चरण 7: टेक्स्ट गुण सेट करें
टेक्स्ट गुणों जैसे फ़ॉन्ट आकार, फ़ॉन्ट प्रकार, पृष्ठभूमि रंग, अग्रभूमि रंग इत्यादि को अनुकूलित करें। दिए गए कोड में, फ़ॉन्ट आकार, फ़ॉन्ट, पृष्ठभूमि रंग, अग्रभूमि रंग और स्ट्रोकिंग रंग जैसे गुण टेक्स्ट टुकड़े के लिए सेट किए गए हैं।

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## चरण 8: टेक्स्ट बॉर्डर सक्षम करें
 टेक्स्ट बॉर्डर सक्षम करने के लिए, सेट करें`DrawTextRectangleBorder`पाठ खंड की संपत्ति`TextState` को`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## चरण 9: पेज पर टेक्स्टफ्रैगमेंट जोड़ें
 उपयोग`TextBuilder` वर्ग को जोड़ने के लिए`TextFragment` पेज पर आपत्ति.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## चरण 10: पीडीएफ दस्तावेज़ सहेजें
 का उपयोग करके पीडीएफ दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु। चरण 3 में आपके द्वारा सेट किया गया आउटपुट फ़ाइल पथ निर्दिष्ट करें।

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट बॉर्डर जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// नया दस्तावेज़ ऑब्जेक्ट बनाएँ
Document pdfDocument = new Document();
// विशेष पृष्ठ प्राप्त करें
Page pdfPage = (Page)pdfDocument.Pages.Add();
// पाठ खंड बनाएँ
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// पाठ गुण सेट करें
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// टेक्स्ट आयत के चारों ओर बॉर्डर (स्ट्रोकिंग) बनाने के लिए StrokingColor प्रॉपर्टी सेट करें
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangelBorder प्रॉपर्टी मान को सत्य पर सेट करें
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके अपने PDF दस्तावेज़ में सफलतापूर्वक एक टेक्स्ट बॉर्डर जोड़ दिया है। परिणामी पीडीएफ फाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का मुख्य फोकस क्या है?

उ: यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फाइल में टेक्स्ट बॉर्डर जोड़ने की प्रक्रिया में आपका मार्गदर्शन करता है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को दर्शाता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने की आवश्यकता है?

उ: कोड फ़ाइल में जहां आप टेक्स्ट बॉर्डर जोड़ना चाहते हैं, फ़ाइल की शुरुआत में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: कोड में, लाइन का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं दस्तावेज़ ऑब्जेक्ट कैसे बनाऊं?

 उ: चरण 4 में, आप एक नया इंस्टेंट करेंगे`Document` कोड की निम्नलिखित पंक्ति का उपयोग करके ऑब्जेक्ट करें:

```csharp
Document pdfDocument = new Document();
```

#### प्रश्न: मैं दस्तावेज़ में एक पृष्ठ कैसे जोड़ूँ?

 उ: चरण 5 में, आप इसका उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### प्रश्न: मैं टेक्स्टफ्रैगमेंट कैसे बनाऊं और उसकी स्थिति कैसे निर्धारित करूं?

 उ: चरण 6 में, आप एक बनाएंगे`TextFragment`ऑब्जेक्ट का उपयोग करें और पृष्ठ पर उसकी स्थिति निर्धारित करें`Position` संपत्ति:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### प्रश्न: मैं टेक्स्ट बॉर्डर सहित टेक्स्ट गुणों को कैसे अनुकूलित कर सकता हूं?

उत्तर: चरण 7 में, आप विभिन्न टेक्स्ट गुणों जैसे फ़ॉन्ट आकार, फ़ॉन्ट प्रकार, पृष्ठभूमि रंग, अग्रभूमि रंग और टेक्स्ट बॉर्डर को अनुकूलित करेंगे:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में टेक्स्टफ्रैगमेंट कैसे जोड़ूं?

 उत्तर: चरण 9 में, आप इसका उपयोग करेंगे`TextBuilder` वर्ग को जोड़ने के लिए`TextFragment` पेज पर आपत्ति:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### प्रश्न: मैं परिणामी पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उत्तर: टेक्स्ट को बॉर्डर के साथ जोड़ने के बाद, इसका उपयोग करें`Save` की विधि`Document` पीडीएफ दस्तावेज़ को सहेजने के लिए ऑब्जेक्ट:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट बॉर्डर जोड़कर अपने पीडीएफ दस्तावेज़ को कैसे बढ़ाया जाए। यह आपकी पीडीएफ फाइलों में विशिष्ट पाठ्य सामग्री पर जोर देने के लिए विशेष रूप से उपयोगी हो सकता है।