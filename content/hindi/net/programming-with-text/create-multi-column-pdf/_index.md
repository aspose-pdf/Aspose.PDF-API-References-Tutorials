---
title: मल्टी कॉलम पीडीएफ बनाएं
linktitle: मल्टी कॉलम पीडीएफ बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके बहु-स्तंभ पीडीएफ बनाना सीखें।
type: docs
weight: 110
url: /hi/net/programming-with-text/create-multi-column-pdf/
---
यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके मल्टी कॉलम पीडीएफ बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। प्रदान किया गया C# स्रोत कोड आवश्यक चरणों को प्रदर्शित करता है।

## आवश्यकताएं
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Visual Studio या कोई अन्य C# कंपाइलर स्थापित होना चाहिए।
- .NET लाइब्रेरी के लिए Aspose.PDF. आप इसे आधिकारिक Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट अप करें
1. अपने पसंदीदा विकास वातावरण में एक नया C# प्रोजेक्ट बनाएं।
2. .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें
उस कोड फ़ाइल में जहाँ आप बहु-स्तंभ पीडीएफ बनाना चाहते हैं, फ़ाइल के शीर्ष पर निम्नलिखित using निर्देश जोड़ें:

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

## चरण 5: पेज मार्जिन सेट करें
 पीडीएफ फाइल के लिए बाएं और दाएं मार्जिन की जानकारी निर्दिष्ट करें`PageInfo.Margin` की संपत्ति`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## चरण 6: दस्तावेज़ में एक पृष्ठ जोड़ें
 दस्तावेज़ में नया पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Add` की विधि`Pages`संग्रह। प्रदान किए गए कोड में, नया पृष्ठ चर को सौंपा गया है`page`.

```csharp
Page page = doc.Pages.Add();
```

## चरण 7: एक ग्राफ़ ऑब्जेक्ट बनाएँ और एक रेखा जोड़ें
 एक नया बनाएँ`Graph` विशिष्ट आयामों वाली वस्तु लें और उसमें एक रेखा जोड़ें। फिर, जोड़ें`Graph` इस पर आपत्ति जताना`Paragraphs` पृष्ठ का संग्रह.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## चरण 8: HTML फ़ॉर्मेटिंग के साथ शीर्षक टेक्स्ट जोड़ें
 एक बनाएं`HtmlFragment` ऑब्जेक्ट और इसकी सामग्री को वांछित HTML टेक्स्ट पर सेट करें। फिर, फ़्रैगमेंट को इसमें जोड़ें`Paragraphs` पृष्ठ का संग्रह.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## चरण 9: एकाधिक कॉलम वाला फ़्लोटिंगबॉक्स बनाएँ
 एक बनाने के`FloatingBox` ऑब्जेक्ट पर जाएं और कॉलम की संख्या और कॉलम स्पेसिंग सेट करें। फिर, टेक्स्ट के टुकड़े और एक लाइन जोड़ें`Paragraphs` का संग्रह`FloatingBox`.

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
 पीडीएफ दस्तावेज़ को सेव करने के लिए निम्न का उपयोग करें:`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके मल्टी कॉलम पीडीएफ बनाने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//पीडीएफ फाइल के लिए बाएं मार्जिन की जानकारी निर्दिष्ट करें
doc.PageInfo.Margin.Left = 40;
// पीडीएफ फाइल के लिए दाएँ मार्जिन की जानकारी निर्दिष्ट करें
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// सेक्शन ऑब्जेक्ट के पैराफ्राफ़्स संग्रह में लाइन जोड़ें
page.Paragraphs.Add(graph1);
// रेखा के लिए निर्देशांक निर्दिष्ट करें
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// HTML टैग वाले टेक्स्ट के साथ स्ट्रिंग वैरिएबल बनाएं
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// HTML टेक्स्ट युक्त टेक्स्ट पैराग्राफ़ बनाएँ
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
// रेखा खींचने के लिए ग्राफ़ ऑब्जेक्ट बनाएँ
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// रेखा के लिए निर्देशांक निर्दिष्ट करें
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// सेक्शन ऑब्जेक्ट के पैराग्राफ़ संग्रह में लाइन जोड़ें
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// पीडीएफ फाइल सहेजें
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
आपने .NET के लिए Aspose.PDF का उपयोग करके सफलतापूर्वक एक बहु-स्तंभ PDF बनाया है। परिणामी PDF फ़ाइल अब निर्दिष्ट आउटपुट फ़ाइल पथ पर पाई जा सकती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का फोकस क्या है?

यह ट्यूटोरियल आपको Aspose.PDF for .NET लाइब्रेरी का उपयोग करके मल्टी-कॉलम पीडीएफ बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करने पर केंद्रित है। प्रदान किया गया C# स्रोत कोड इसे प्राप्त करने के लिए आवश्यक चरणों को प्रदर्शित करता है।

#### प्रश्न: इस ट्यूटोरियल के लिए मुझे कौन से नेमस्पेस आयात करने चाहिए?

उत्तर: उस कोड फ़ाइल में जहाँ आप बहु-स्तंभ पीडीएफ बनाना चाहते हैं, फ़ाइल के आरंभ में निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे निर्दिष्ट करूँ?

 उत्तर: कोड में, पंक्ति ढूंढें`string dataDir = "YOUR DOCUMENT DIRECTORY";` और प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

#### प्रश्न: मैं नया दस्तावेज़ उदाहरण कैसे बनाऊं?

 उत्तर: चरण 4 में, आप एक नया इन्स्टेन्सिएट करेंगे`Document` दिए गए कोड का उपयोग करके ऑब्जेक्ट को चिह्नित करें।

#### प्रश्न: मैं पृष्ठ मार्जिन कैसे निर्धारित करूँ?

 उत्तर: चरण 5 में, आप इसका उपयोग करेंगे`PageInfo.Margin` की संपत्ति`Document` पीडीएफ फाइल के लिए बाएं और दाएं मार्जिन की जानकारी निर्दिष्ट करने के लिए।

#### प्रश्न: मैं दस्तावेज़ में पृष्ठ कैसे जोड़ूं?

 उत्तर: चरण 6 में, आप दस्तावेज़ में एक नया पृष्ठ जोड़ेंगे`Add` की विधि`Pages` संग्रह।

#### प्रश्न: मैं ग्राफ ऑब्जेक्ट कैसे बनाऊं और उसमें रेखा कैसे जोड़ूं?

 उत्तर: चरण 7 में, आप एक नया बनाएंगे`Graph` ऑब्जेक्ट, इसमें एक पंक्ति जोड़ें, और फिर जोड़ें`Graph` इस पर आपत्ति जताना`Paragraphs` पृष्ठ का संग्रह.

#### प्रश्न: मैं HTML स्वरूपण के साथ शीर्षक पाठ कैसे जोड़ूं?

 उत्तर: चरण 8 में, आप एक बनाएंगे`HtmlFragment` ऑब्जेक्ट और इसकी सामग्री को वांछित HTML पाठ पर सेट करें, फिर खंड को इसमें जोड़ें`Paragraphs` पृष्ठ का संग्रह.

#### प्रश्न: मैं एकाधिक कॉलम वाला फ्लोटिंगबॉक्स कैसे बनाऊं?

 उत्तर: चरण 9 में, आप एक बनाएंगे`FloatingBox` एकाधिक स्तंभों और स्तंभ रिक्तियों के साथ ऑब्जेक्ट, फिर पाठ टुकड़े और एक पंक्ति जोड़ें`Paragraphs` का संग्रह`FloatingBox`.

#### प्रश्न: मैं पीडीएफ दस्तावेज़ कैसे सहेजूं?

 उत्तर: चरण 10 में, आप PDF दस्तावेज़ को निम्न का उपयोग करके सहेजेंगे`Save` की विधि`Document` वस्तु।

#### प्रश्न: इस ट्यूटोरियल से मुख्य बात क्या है?

उत्तर: इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके एक बहु-स्तंभ PDF दस्तावेज़ कैसे बनाया जाता है। यह संरचित और संगठित लेआउट में सामग्री प्रदर्शित करने के लिए उपयोगी हो सकता है।