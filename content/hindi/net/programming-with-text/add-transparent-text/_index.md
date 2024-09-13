---
title: पीडीएफ फाइल में पारदर्शी टेक्स्ट जोड़ें
linktitle: पीडीएफ फाइल में पारदर्शी टेक्स्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में पारदर्शी पाठ जोड़ने का तरीका जानें।
type: docs
weight: 100
url: /hi/net/programming-with-text/add-transparent-text/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में पारदर्शी पाठ जोड़ने की प्रक्रिया के बारे में बताएगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप पारदर्शी पाठ जोड़ना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: एक नया दस्तावेज़ इंस्टेंस बनाएँ
 एक नया उदाहरण बनाएँ`Document` निम्न कोड पंक्ति जोड़कर ऑब्जेक्ट बनाएँ:

```csharp
Document doc = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में एक नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages` संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## चरण 6: एक ग्राफ़ ऑब्जेक्ट बनाएँ
 एक नया बनाएँ`Graph` एक विशिष्ट चौड़ाई और ऊंचाई वाली वस्तु।

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## चरण 7: पारदर्शिता के साथ एक आयत बनाएं
 विशिष्ट आयामों के साथ एक आयत बनाएं और इसका भरण रंग पारदर्शी रंग में सेट करें`Color.FromRgb` तरीका।

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## चरण 8: पृष्ठ पर ग्राफ़ ऑब्जेक्ट जोड़ें
 जोड़ें`Graph` पृष्ठ के पैराग्राफ संग्रह पर आपत्ति।

```csharp
page.Paragraphs.Add(canvas);
```

## चरण 9: ग्राफ़ ऑब्जेक्ट के लिए स्थिति सेट करें
 सेट करें`IsChangePosition` की संपत्ति`Graph` करने के लिए वस्तु`false` इसे अपनी स्थिति बदलने से रोकने के लिए।

```csharp
canvas. IsChangePosition = false;
```

## चरण 10: पारदर्शिता के साथ एक टेक्स्टफ़्रेगमेंट बनाएँ
 एक बनाने के`TextFragment` ऑब्जेक्ट और इसकी सामग्री को वांछित पाठ पर सेट करें।`ForegroundColor` की संपत्ति`TextState` पारदर्शिता के साथ एक रंग के लिए`Color.FromArgb` तरीका।

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## चरण 11: PDF दस्तावेज़ सहेजें
 पीडीएफ दस्तावेज़ को सेव करने के लिए निम्न का उपयोग करें:`Save` की विधि`Document` वस्तु।

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
// ग्राफ ऑब्जेक्ट बनाएँ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// निश्चित आयामों के साथ आयत उदाहरण बनाएँ
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// अल्फा कलर चैनल से रंग ऑब्जेक्ट बनाएं
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// ग्राफ ऑब्जेक्ट के आकार संग्रह में आयत जोड़ें
canvas.Shapes.Add(rect);
// पेज ऑब्जेक्ट के पैराग्राफ़ संग्रह में ग्राफ़ ऑब्जेक्ट जोड़ें
page.Paragraphs.Add(canvas);
// ग्राफ़ ऑब्जेक्ट की स्थिति न बदलने के लिए मान सेट करें
canvas.IsChangePosition = false;
// नमूना मान के साथ TextFragment इंस्टेंस बनाएँ
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// अल्फा चैनल से रंग ऑब्जेक्ट बनाएँ
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// टेक्स्ट इंस्टेंस के लिए रंग जानकारी सेट करें
text.TextState.ForegroundColor = color;
// पृष्ठ उदाहरण के पैराग्राफ़ संग्रह में पाठ जोड़ें
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके अपने PDF दस्तावेज़ में सफलतापूर्वक पारदर्शी पाठ जोड़ लिया है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

उत्तर: यह ट्यूटोरियल Aspose.PDF for .NET लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में पारदर्शी टेक्स्ट जोड़ने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इस प्रभाव को प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए कौन से नेमस्पेस को आयात करने की आवश्यकता है?

उत्तर: उस कोड फ़ाइल में जहाँ आप पारदर्शी पाठ जोड़ना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उत्तर: चरण 4 में, आप एक नया इन्स्टेन्सिएट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट को चिह्नित करें।

#### प्रश्न: मैं दस्तावेज़ में पृष्ठ कैसे जोड़ूं?

 उत्तर: चरण 5 में, आप दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं ग्राफ ऑब्जेक्ट कैसे बनाऊं?

 उत्तर: चरण 6 में, आप एक नया बनाएंगे`Graph` एक विशिष्ट चौड़ाई और ऊंचाई वाली वस्तु।

#### प्रश्न: मैं पारदर्शिता के साथ आयत कैसे बनाऊं?

 उत्तर: चरण 7 में, आप विशिष्ट आयामों के साथ एक आयत बनाएंगे और इसका भरण रंग पारदर्शी रंग में सेट करेंगे।`Color.FromRgb` तरीका।

#### प्रश्न: मैं पेज पर ग्राफ ऑब्जेक्ट कैसे जोड़ूं?

 उत्तर: चरण 8 में, आप जोड़ेंगे`Graph` पृष्ठ के पैराग्राफ संग्रह पर आपत्ति।

#### प्रश्न: मैं ग्राफ ऑब्जेक्ट के लिए स्थिति कैसे निर्धारित करूं?

 उत्तर: चरण 9 में, आप सेट करेंगे`IsChangePosition` की संपत्ति`Graph` करने के लिए वस्तु`false` इसे अपनी स्थिति बदलने से रोकने के लिए।

#### प्रश्न: मैं पारदर्शिता के साथ टेक्स्टफ़्रेगमेंट कैसे बनाऊं?

उत्तर: चरण 10 में, आप एक बनाएंगे`TextFragment` ऑब्जेक्ट और इसकी सामग्री सेट करें और`ForegroundColor` पारदर्शी पाठ प्राप्त करने के लिए संपत्ति।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ कैसे सहेजूं?

 उत्तर: चरण 11 में, आप PDF दस्तावेज़ को निम्न का उपयोग करके सहेजेंगे`Save` की विधि`Document` वस्तु।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में पारदर्शी टेक्स्ट कैसे जोड़ा जाता है। यह दिखने में आकर्षक और रचनात्मक PDF दस्तावेज़ बनाने के लिए उपयोगी हो सकता है।