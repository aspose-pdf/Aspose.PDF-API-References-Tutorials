---
title: पीडीएफ फाइल में कस्टम टैब स्टॉप
linktitle: पीडीएफ फाइल में कस्टम टैब स्टॉप
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कस्टम टैब स्टॉप बनाने का तरीका जानें।
type: docs
weight: 120
url: /hi/net/programming-with-text/custom-tab-stops/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कस्टम टैब स्टॉप बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को प्रदर्शित करता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप कस्टम टैब स्टॉप बनाना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका सेट करें
 कोड में, वह पंक्ति ढूंढें जो कहती है`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का पथ जहां आपके दस्तावेज़ संग्रहीत हैं.

## चरण 4: एक नया दस्तावेज़ इंस्टेंस बनाएँ
 एक नया उदाहरण बनाएँ`Document` निम्न कोड पंक्ति जोड़कर ऑब्जेक्ट बनाएँ:

```csharp
Document _pdfdocument = new Document();
```

## चरण 5: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages`संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## चरण 6: कस्टम टैब स्टॉप बनाएं
 एक बनाने के`TabStops` ऑब्जेक्ट पर क्लिक करें और उसमें कस्टम टैब स्टॉप जोड़ें। प्रत्येक टैब स्टॉप के लिए संरेखण प्रकार और लीडर प्रकार सेट करें।

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## चरण 7: टैब स्टॉप के साथ टेक्स्ट अंश बनाएँ
 बनाएं`TextFragment` ऑब्जेक्ट्स को चुनें और उन्हें कस्टम टैब स्टॉप पास करें। विशेष वर्णों का उपयोग करें`#$TAB` पाठ के भीतर टैब स्टॉप को इंगित करने के लिए.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## चरण 8: पीडीएफ दस्तावेज़ सहेजें
 पीडीएफ दस्तावेज़ को सेव करने के लिए निम्न का उपयोग करें:`Save` की विधि`Document` वस्तु।

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके कस्टम टैब स्टॉप के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके कस्टम टैब स्टॉप के साथ सफलतापूर्वक एक PDF दस्तावेज़ बनाया है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

उत्तर: यह ट्यूटोरियल आपको .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कस्टम टैब स्टॉप बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने चाहिए?

उत्तर: उस कोड फ़ाइल में जहाँ आप कस्टम टैब स्टॉप बनाना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उत्तर: चरण 4 में, आप एक नया इन्स्टेन्सिएट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट को चिह्नित करें।

#### प्रश्न: मैं दस्तावेज़ में पृष्ठ कैसे जोड़ूं?

 उत्तर: चरण 5 में, आप दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं कस्टम टैब स्टॉप कैसे बनाऊं?

 उत्तर: चरण 6 में, आप एक बनाएंगे`TabStops` ऑब्जेक्ट चुनें और उसमें कस्टम टैब स्टॉप जोड़ें। आप प्रत्येक टैब स्टॉप के लिए संरेखण और लीडर प्रकार भी सेट करेंगे।

#### प्रश्न: मैं टैब स्टॉप के साथ पाठ अंश कैसे बनाऊं?

 उत्तर: चरण 7 में, आप बनाएंगे`TextFragment` ऑब्जेक्ट्स और उन्हें कस्टम टैब स्टॉप पास करें। आप विशेष वर्णों का उपयोग करेंगे`#$TAB` पाठ के भीतर टैब स्टॉप को इंगित करने के लिए.

#### प्रश्न: मैं पीडीएफ दस्तावेज़ कैसे सहेजूं?

 उत्तर: चरण 8 में, आप PDF दस्तावेज़ को निम्न का उपयोग करके सहेजेंगे:`Save` की विधि`Document` वस्तु।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके कस्टम टैब स्टॉप के साथ PDF दस्तावेज़ कैसे बनाया जाता है। यह संरचित तरीके से टेक्स्ट को व्यवस्थित और संरेखित करने के लिए उपयोगी हो सकता है।