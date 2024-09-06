---
title: पीडीएफ फाइल में टेक्स्ट बॉर्डर जोड़ें
linktitle: पीडीएफ फाइल में टेक्स्ट बॉर्डर जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट बॉर्डर जोड़ने का तरीका जानें।
type: docs
weight: 70
url: /hi/net/programming-with-text/add-text-border/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट बॉर्डर जोड़ने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप टेक्स्ट बॉर्डर जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: एक नया दस्तावेज़ ऑब्जेक्ट बनाएँ
 एक नया उदाहरण बनाएँ`Document` निम्न कोड पंक्ति जोड़कर ऑब्जेक्ट बनाएँ:

```csharp
Document pdfDocument = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में एक नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages`संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## चरण 6: एक टेक्स्टफ़्रेगमेंट बनाएँ
 एक बनाने के`TextFragment` ऑब्जेक्ट और वांछित टेक्स्ट प्रदान करें। टेक्स्ट फ़्रैगमेंट की स्थिति को सेट करने के लिए इसका उपयोग करें`Position` संपत्ति। प्रदान किए गए कोड में, पाठ को "मुख्य पाठ" पर सेट किया गया है और पृष्ठ पर (100, 600) पर स्थित किया गया है।

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## चरण 7: पाठ गुण सेट करें
फ़ॉन्ट आकार, फ़ॉन्ट प्रकार, पृष्ठभूमि रंग, अग्रभूमि रंग आदि जैसे पाठ गुणों को अनुकूलित करें। प्रदान किए गए कोड में, फ़ॉन्ट आकार, फ़ॉन्ट, पृष्ठभूमि रंग, अग्रभूमि रंग और स्ट्रोकिंग रंग जैसे गुण पाठ खंड के लिए सेट किए गए हैं।

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## चरण 8: टेक्स्ट बॉर्डर सक्षम करें
 टेक्स्ट बॉर्डर को सक्षम करने के लिए, सेट करें`DrawTextRectangleBorder`पाठ खंड की संपत्ति`TextState` को`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## चरण 9: पृष्ठ पर टेक्स्टफ़्रेगमेंट जोड़ें
 उपयोग`TextBuilder` वर्ग जोड़ने के लिए`TextFragment` पृष्ठ पर आपत्ति जताएं.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## चरण 10: पीडीएफ दस्तावेज़ सहेजें
 पीडीएफ दस्तावेज़ को सेव करने के लिए निम्न का उपयोग करें:`Save` की विधि`Document` ऑब्जेक्ट. चरण 3 में आपके द्वारा सेट किया गया आउटपुट फ़ाइल पथ निर्दिष्ट करें.

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
// पाठ आयत के चारों ओर बॉर्डर (स्ट्रोकिंग) खींचने के लिए स्ट्रोकिंग कलर गुण सेट करें
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorder गुण मान को true पर सेट करें
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके अपने PDF दस्तावेज़ में सफलतापूर्वक एक टेक्स्ट बॉर्डर जोड़ लिया है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का मुख्य फोकस क्या है?

उत्तर: यह ट्यूटोरियल आपको .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में टेक्स्ट बॉर्डर जोड़ने की प्रक्रिया के बारे में बताता है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने होंगे?

उत्तर: उस कोड फ़ाइल में जहाँ आप टेक्स्ट बॉर्डर जोड़ना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति का पता लगाएं`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं दस्तावेज़ ऑब्जेक्ट कैसे बनाऊं?

 उत्तर: चरण 4 में, आप एक नया इन्स्टेन्सिएट करेंगे`Document` निम्न कोड लाइन का उपयोग करके ऑब्जेक्ट बनाएँ:

```csharp
Document pdfDocument = new Document();
```

#### प्रश्न: मैं दस्तावेज़ में पृष्ठ कैसे जोड़ूं?

 उत्तर: चरण 5 में, आप दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### प्रश्न: मैं टेक्स्टफ़्रेगमेंट कैसे बनाऊं और उसकी स्थिति कैसे निर्धारित करूं?

 उत्तर: चरण 6 में, आप एक बनाएंगे`TextFragment`ऑब्जेक्ट और पृष्ठ पर इसकी स्थिति निर्धारित करें`Position` संपत्ति:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### प्रश्न: मैं टेक्स्ट बॉर्डर सहित टेक्स्ट गुणों को कैसे अनुकूलित कर सकता हूं?

उत्तर: चरण 7 में, आप विभिन्न पाठ गुणों को अनुकूलित करेंगे, जैसे फ़ॉन्ट आकार, फ़ॉन्ट प्रकार, पृष्ठभूमि रंग, अग्रभूमि रंग और पाठ बॉर्डर:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### प्रश्न: मैं PDF दस्तावेज़ में TextFragment कैसे जोड़ूं?

 उत्तर: चरण 9 में, आप इसका उपयोग करेंगे`TextBuilder` वर्ग जोड़ने के लिए`TextFragment` पृष्ठ पर आपत्ति:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### प्रश्न: मैं परिणामी पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: बॉर्डर के साथ टेक्स्ट जोड़ने के बाद, का उपयोग करें`Save` की विधि`Document` पीडीएफ दस्तावेज़ को सहेजने के लिए ऑब्जेक्ट:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सफलतापूर्वक सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट बॉर्डर जोड़कर अपने PDF दस्तावेज़ को कैसे बेहतर बनाया जाए। यह आपकी PDF फ़ाइलों के भीतर विशिष्ट टेक्स्ट सामग्री पर ज़ोर देने के लिए विशेष रूप से उपयोगी हो सकता है।