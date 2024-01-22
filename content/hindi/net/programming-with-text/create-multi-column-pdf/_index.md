---
title: मल्टी कॉलम पीडीएफ बनाएं
linktitle: मल्टी कॉलम पीडीएफ बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके मल्टी कॉलम पीडीएफ बनाना सीखें।
type: docs
weight: 110
url: /hi/net/programming-with-text/create-multi-column-pdf/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके मल्टी कॉलम पीडीएफ बनाने की प्रक्रिया में मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को दर्शाता है।

## आवश्यकताएं
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या आपकी मशीन पर कोई अन्य C# कंपाइलर स्थापित।
- .NET लाइब्रेरी के लिए Aspose.PDF। आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें
1. अपने पसंदीदा विकास परिवेश में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
कोड फ़ाइल में जहां आप एक मल्टी कॉलम पीडीएफ बनाना चाहते हैं, फ़ाइल के शीर्ष पर निर्देशों का उपयोग करके निम्नलिखित जोड़ें:

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

## चरण 5: पेज मार्जिन सेट करें
 का उपयोग करके पीडीएफ फ़ाइल के लिए बाएँ और दाएँ मार्जिन की जानकारी निर्दिष्ट करें`PageInfo.Margin` की संपत्ति`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## चरण 6: दस्तावेज़ में एक पृष्ठ जोड़ें
 का उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ें`Add` की विधि`Pages`संग्रह। दिए गए कोड में, नया पेज वेरिएबल को सौंपा गया है`page`.

```csharp
Page page = doc.Pages.Add();
```

## चरण 7: एक ग्राफ़ ऑब्जेक्ट बनाएं और एक पंक्ति जोड़ें
 कोई नया बनाएं`Graph` विशिष्ट आयामों वाली वस्तु बनाएं और उसमें एक पंक्ति जोड़ें। फिर, जोड़ें`Graph` पर आपत्ति है`Paragraphs` पेज का संग्रह.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## चरण 8: HTML फ़ॉर्मेटिंग के साथ शीर्षक टेक्स्ट जोड़ें
 एक बनाएं`HtmlFragment` ऑब्जेक्ट बनाएं और उसकी सामग्री को वांछित HTML टेक्स्ट पर सेट करें। फिर, टुकड़े को इसमें जोड़ें`Paragraphs` पेज का संग्रह.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## चरण 9: एकाधिक कॉलम वाला एक फ़्लोटिंगबॉक्स बनाएं
 एक बनाने के`FloatingBox` ऑब्जेक्ट करें और कॉलम की संख्या और कॉलम रिक्ति निर्धारित करें। फिर, इसमें टेक्स्ट के टुकड़े और एक पंक्ति जोड़ें`Paragraphs` का संग्रह`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## चरण 10: पीडीएफ दस्तावेज़ सहेजें
 का उपयोग करके पीडीएफ दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके मल्टी कॉलम पीडीएफ बनाने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// पीडीएफ फ़ाइल के लिए बाएँ मार्जिन की जानकारी निर्दिष्ट करें
doc.PageInfo.Margin.Left = 40;
//पीडीएफ फाइल के लिए राइट मार्जिन जानकारी निर्दिष्ट करें
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// सेक्शन ऑब्जेक्ट के पैराग्राफ संग्रह में लाइन जोड़ें
page.Paragraphs.Add(graph1);
// रेखा के लिए निर्देशांक निर्दिष्ट करें
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// HTML टैग वाले टेक्स्ट के साथ स्ट्रिंग वेरिएबल बनाएं
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// HTML टेक्स्ट वाले टेक्स्ट पैराग्राफ बनाएं
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// अनुभाग में चार कॉलम जोड़ें
box.ColumnInfo.ColumnCount = 2;
// स्तंभों के बीच अंतर निर्धारित करें
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// एक रेखा खींचने के लिए एक ग्राफ़ ऑब्जेक्ट बनाएं
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// रेखा के लिए निर्देशांक निर्दिष्ट करें
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// सेक्शन ऑब्जेक्ट के पैराग्राफ़ संग्रह में पंक्ति जोड़ें
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// पीडीएफ फाइल सेव करें
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके सफलतापूर्वक एक मल्टी कॉलम पीडीएफ बनाया है। परिणामी पीडीएफ फाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

यह ट्यूटोरियल .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके मल्टी-कॉलम पीडीएफ बनाने की प्रक्रिया में आपका मार्गदर्शन करने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को दर्शाता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने चाहिए?

उ: कोड फ़ाइल में जहां आप एक मल्टी-कॉलम पीडीएफ बनाना चाहते हैं, फ़ाइल की शुरुआत में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूं?

 ए: कोड में, लाइन ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और बदलें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं एक नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उ: चरण 4 में, आप एक नया इंस्टेंट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट करें।

#### प्रश्न: मैं पेज मार्जिन कैसे सेट करूं?

 उत्तर: चरण 5 में, आप इसका उपयोग करेंगे`PageInfo.Margin` की संपत्ति`Document` पीडीएफ फ़ाइल के लिए बाएँ और दाएँ मार्जिन की जानकारी निर्दिष्ट करने के लिए।

#### प्रश्न: मैं दस्तावेज़ में एक पृष्ठ कैसे जोड़ूँ?

 उ: चरण 6 में, आप इसका उपयोग करके दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं ग्राफ़ ऑब्जेक्ट कैसे बनाऊं और एक पंक्ति कैसे जोड़ूं?

 उ: चरण 7 में, आप एक नया बनाएंगे`Graph` ऑब्जेक्ट, उसमें एक पंक्ति जोड़ें, और फिर जोड़ें`Graph` पर आपत्ति है`Paragraphs` पेज का संग्रह.

#### प्रश्न: मैं HTML फ़ॉर्मेटिंग के साथ शीर्षक टेक्स्ट कैसे जोड़ूँ?

 उ: चरण 8 में, आप एक बनाएंगे`HtmlFragment` ऑब्जेक्ट बनाएं और उसकी सामग्री को वांछित HTML टेक्स्ट पर सेट करें, फिर उसमें फ़्रैगमेंट जोड़ें`Paragraphs` पेज का संग्रह.

#### प्रश्न: मैं एकाधिक कॉलम वाला फ़्लोटिंगबॉक्स कैसे बना सकता हूँ?

 उ: चरण 9 में, आप एक बनाएंगे`FloatingBox` एकाधिक कॉलम और कॉलम रिक्ति वाला ऑब्जेक्ट, फिर टेक्स्ट टुकड़े और एक पंक्ति जोड़ें`Paragraphs` का संग्रह`FloatingBox`.

#### प्रश्न: मैं पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उ: चरण 10 में, आप इसका उपयोग करके पीडीएफ दस्तावेज़ को सहेजेंगे`Save` की विधि`Document` वस्तु।

#### प्रश्न: इस ट्यूटोरियल से मुख्य निष्कर्ष क्या है?

उ: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके एक मल्टी-कॉलम पीडीएफ दस्तावेज़ कैसे बनाया जाए। यह सामग्री को संरचित और व्यवस्थित लेआउट में प्रदर्शित करने के लिए उपयोगी हो सकता है।