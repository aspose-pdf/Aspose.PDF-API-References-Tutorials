---
title: पीडीएफ फाइल में पारदर्शी टेक्स्ट जोड़ें
linktitle: पीडीएफ फाइल में पारदर्शी टेक्स्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पारदर्शी टेक्स्ट जोड़ने का तरीका जानें।
type: docs
weight: 100
url: /hi/net/programming-with-text/add-transparent-text/
---
यह ट्यूटोरियल .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में पारदर्शी पाठ जोड़ने की प्रक्रिया में आपका मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप पारदर्शी टेक्स्ट जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके निम्नलिखित जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, उस पंक्ति का पता लगाएं जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपके दस्तावेज़ संग्रहीत हैं।

## चरण 4: एक नया दस्तावेज़ उदाहरण बनाएँ
 एक नया त्वरित करें`Document` कोड की निम्नलिखित पंक्ति जोड़कर ऑब्जेक्ट करें:

```csharp
Document doc = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 का उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ें`Add` की विधि`Pages`संग्रह। दिए गए कोड में, नया पेज वेरिएबल को सौंपा गया है`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## चरण 6: एक ग्राफ़ ऑब्जेक्ट बनाएं
 कोई नया बनाएं`Graph` एक विशिष्ट चौड़ाई और ऊंचाई वाली वस्तु।

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## चरण 7: पारदर्शिता के साथ एक आयत बनाएं
 विशिष्ट आयामों के साथ एक आयत बनाएं और इसका उपयोग करके इसके भरण रंग को पारदर्शी रंग में सेट करें`Color.FromRgb` तरीका।

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## चरण 8: ग्राफ़ ऑब्जेक्ट को पृष्ठ पर जोड़ें
 जोड़ें`Graph` पृष्ठ के अनुच्छेद संग्रह पर आपत्ति।

```csharp
page.Paragraphs.Add(canvas);
```

## चरण 9: ग्राफ़ ऑब्जेक्ट के लिए स्थिति निर्धारित करें
 ठीक`IsChangePosition` की संपत्ति`Graph` करने के लिए वस्तु`false` इसे स्थिति बदलने से रोकने के लिए.

```csharp
canvas. IsChangePosition = false;
```

## चरण 10: पारदर्शिता के साथ एक टेक्स्टफ़्रैगमेंट बनाएं
 एक बनाने के`TextFragment` ऑब्जेक्ट बनाएं और उसकी सामग्री को वांछित टेक्स्ट पर सेट करें। ठीक`ForegroundColor` की संपत्ति`TextState` का उपयोग करके पारदर्शिता के साथ एक रंग प्राप्त करना`Color.FromArgb` तरीका।

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## चरण 11: पीडीएफ दस्तावेज़ सहेजें
 का उपयोग करके पीडीएफ दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके पारदर्शी टेक्स्ट जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ उदाहरण बनाएँ
Document doc = new Document();
// पीडीएफ फाइल का पेज दर पेज संग्रह बनाएं
Aspose.Pdf.Page page = doc.Pages.Add();
// ग्राफ़ ऑब्जेक्ट बनाएं
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// कुछ आयामों के साथ आयत उदाहरण बनाएँ
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// अल्फा कलर चैनल से कलर ऑब्जेक्ट बनाएं
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// ग्राफ़ ऑब्जेक्ट के आकार संग्रह में आयत जोड़ें
canvas.Shapes.Add(rect);
//पेज ऑब्जेक्ट के पैराग्राफ संग्रह में ग्राफ़ ऑब्जेक्ट जोड़ें
page.Paragraphs.Add(canvas);
// ग्राफ़ ऑब्जेक्ट के लिए स्थिति न बदलने के लिए मान सेट करें
canvas.IsChangePosition = false;
// नमूना मान के साथ TextFragment उदाहरण बनाएं
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// अल्फ़ा चैनल से रंगीन ऑब्जेक्ट बनाएं
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// टेक्स्ट उदाहरण के लिए रंग जानकारी सेट करें
text.TextState.ForegroundColor = color;
// पेज इंस्टेंस के पैराग्राफ संग्रह में टेक्स्ट जोड़ें
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके अपने PDF दस्तावेज़ में सफलतापूर्वक पारदर्शी पाठ जोड़ा है। परिणामी पीडीएफ फाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

उ: यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में पारदर्शी पाठ जोड़ने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इस प्रभाव को प्राप्त करने के लिए आवश्यक चरणों को दर्शाता है।

#### प्रश्न: इस ट्यूटोरियल के लिए कौन से नामस्थान आयात करने की आवश्यकता है?

उ: कोड फ़ाइल में जहां आप पारदर्शी टेक्स्ट जोड़ना चाहते हैं, फ़ाइल की शुरुआत में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: कोड में, लाइन ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं एक नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उ: चरण 4 में, आप एक नया इंस्टेंट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट करें।

#### प्रश्न: मैं दस्तावेज़ में एक पृष्ठ कैसे जोड़ूँ?

 उ: चरण 5 में, आप इसका उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं ग्राफ़ ऑब्जेक्ट कैसे बनाऊं?

 उ: चरण 6 में, आप एक नया बनाएंगे`Graph` एक विशिष्ट चौड़ाई और ऊंचाई वाली वस्तु।

#### प्रश्न: मैं पारदर्शिता के साथ एक आयत कैसे बनाऊं?

उत्तर: चरण 7 में, आप विशिष्ट आयामों के साथ एक आयत बनाएंगे और इसका उपयोग करके इसके भरण रंग को पारदर्शी रंग में सेट करेंगे।`Color.FromRgb` तरीका।

#### प्रश्न: मैं पृष्ठ पर ग्राफ़ ऑब्जेक्ट कैसे जोड़ूँ?

 उ: चरण 8 में, आप जोड़ देंगे`Graph` पृष्ठ के अनुच्छेद संग्रह पर आपत्ति।

#### प्रश्न: मैं ग्राफ़ ऑब्जेक्ट के लिए स्थिति कैसे निर्धारित करूं?

 उ: चरण 9 में, आप सेट करेंगे`IsChangePosition` की संपत्ति`Graph` करने के लिए वस्तु`false` इसे स्थिति बदलने से रोकने के लिए.

#### प्रश्न: मैं पारदर्शिता के साथ टेक्स्टफ़्रैगमेंट कैसे बना सकता हूँ?

 उ: चरण 10 में, आप एक बनाएंगे`TextFragment` ऑब्जेक्ट करें और उसकी सामग्री सेट करें और`ForegroundColor` पारदर्शी पाठ प्राप्त करने की संपत्ति।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उ: चरण 11 में, आप इसका उपयोग करके पीडीएफ दस्तावेज़ को सहेजेंगे`Save` की विधि`Document` वस्तु।

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में पारदर्शी टेक्स्ट कैसे जोड़ा जाए। यह देखने में आकर्षक और रचनात्मक पीडीएफ दस्तावेज़ बनाने के लिए उपयोगी हो सकता है।