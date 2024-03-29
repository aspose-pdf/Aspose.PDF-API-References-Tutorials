---
title: पीडीएफ फाइल में लाइन ऑब्जेक्ट जोड़ें
linktitle: पीडीएफ फाइल में लाइन ऑब्जेक्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में कस्टम लाइन ऑब्जेक्ट जोड़ने का तरीका जानें।
type: docs
weight: 30
url: /hi/net/programming-with-graphs/add-line-object/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक लाइन ऑब्जेक्ट जोड़ने के लिए चरण दर चरण निम्नलिखित C# स्रोत कोड के बारे में बताएंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना विकास वातावरण स्थापित कर लिया है। C# प्रोग्रामिंग का बुनियादी ज्ञान भी हो।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए स्रोत कोड में, आपको वह निर्देशिका निर्दिष्ट करनी होगी जहां आप परिणामी पीडीएफ फ़ाइल को सहेजना चाहते हैं। "डेटाडिर" वेरिएबल को वांछित निर्देशिका में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक दस्तावेज़ उदाहरण बनाना और एक पेज जोड़ना

हम दस्तावेज़ वर्ग का एक उदाहरण बनाते हैं और इस दस्तावेज़ में एक पृष्ठ जोड़ते हैं।

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## चरण 3: एक ग्राफ़ ऑब्जेक्ट बनाना और उसे पेज पर जोड़ना

हम निर्दिष्ट आयामों के साथ एक ग्राफ़ ऑब्जेक्ट बनाते हैं और इसे पृष्ठ के पैराग्राफ संग्रह में जोड़ते हैं।

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## चरण 4: लाइन ऑब्जेक्ट बनाएं और चार्ट में जोड़ें

हम निर्दिष्ट निर्देशांक के साथ एक लाइन ऑब्जेक्ट बनाते हैं और इसे चार्ट के आकार संग्रह में जोड़ते हैं।

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## चरण 5: लाइन सेटअप

हम लाइन के लिए गुण निर्दिष्ट कर सकते हैं, जैसे डैश प्रकार और डैश चरण।

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## चरण 6: पीडीएफ फाइल को सहेजना

अंत में, हम परिणामी पीडीएफ फाइल को निर्दिष्ट निर्देशिका में "AddLineObject_out.pdf" नाम से सहेजते हैं।

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके लाइन ऑब्जेक्ट जोड़ने के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ उदाहरण बनाएँ
Document doc = new Document();
// पीडीएफ फाइल के पेज संग्रह में पेज जोड़ें
Page page = doc.Pages.Add();
// ग्राफ़ उदाहरण बनाएँ
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// पृष्ठ उदाहरण के पैराग्राफ संग्रह में ग्राफ़ ऑब्जेक्ट जोड़ें
page.Paragraphs.Add(graph);
// आयत उदाहरण बनाएँ
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// ग्राफ़ ऑब्जेक्ट के लिए भरण रंग निर्दिष्ट करें
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// ग्राफ़ ऑब्जेक्ट के आकार संग्रह में आयताकार ऑब्जेक्ट जोड़ें
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// पीडीएफ फाइल सेव करें
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने चरण दर चरण समझाया है कि .NET के लिए Aspose.PDF का उपयोग करके एक लाइन ऑब्जेक्ट कैसे जोड़ा जाए। अब आप इस ज्ञान का उपयोग अपने अनुप्रयोगों में कस्टम लाइनों के साथ पीडीएफ दस्तावेज़ बनाने के लिए कर सकते हैं।

### पीडीएफ फाइल में लाइन ऑब्जेक्ट जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उ: इस ट्यूटोरियल का उद्देश्य आपके पीडीएफ दस्तावेज़ों को बढ़ाने के लिए .NET के लिए Aspose.PDF का उपयोग करके एक लाइन ऑब्जेक्ट जोड़ने की प्रक्रिया में आपका मार्गदर्शन करना है।

#### प्रश्न: शुरू करने से पहले क्या आवश्यक शर्तें आवश्यक हैं?

उ: शुरू करने से पहले, सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और अपना विकास वातावरण स्थापित कर लिया है। इसके अतिरिक्त, C# प्रोग्रामिंग की बुनियादी समझ रखने की अनुशंसा की जाती है।

#### प्रश्न: मैं पीडीएफ फ़ाइल को सहेजने के लिए निर्देशिका कैसे निर्दिष्ट करूं?

उ: दिए गए स्रोत कोड में, आप उस निर्देशिका को इंगित करने के लिए "डेटाडिर" वेरिएबल को संशोधित कर सकते हैं जहां आप परिणामी पीडीएफ फाइल को सहेजना चाहते हैं।

#### प्रश्न: ग्राफ़ ऑब्जेक्ट का उद्देश्य क्या है?

ए: ग्राफ़ ऑब्जेक्ट ड्राइंग तत्वों के लिए एक कंटेनर के रूप में कार्य करता है। इसे निर्दिष्ट आयामों के साथ बनाया जाता है और पृष्ठ के पैराग्राफ संग्रह में जोड़ा जाता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में एक लाइन ऑब्जेक्ट कैसे जोड़ सकता हूं?

ए: एक लाइन ऑब्जेक्ट जोड़ने के लिए, निर्दिष्ट निर्देशांक के साथ लाइन क्लास का एक उदाहरण बनाएं और इसे ग्राफ़ के आकार संग्रह में जोड़ें।

#### प्रश्न: क्या मैं लाइन के स्वरूप को अनुकूलित कर सकता हूँ?

उ: हां, आप लाइन ऑब्जेक्ट की ग्राफइन्फो प्रॉपर्टी का उपयोग करके डैश प्रकार और डैश चरण जैसे गुणों को सेट करके लाइन की उपस्थिति को अनुकूलित कर सकते हैं।

#### प्रश्न: डैश ऐरे और डैश चरण को निर्दिष्ट करने का उद्देश्य क्या है?

उ: डैश सरणी और डैश चरण गुण आपको विशिष्ट पैटर्न के साथ धराशायी या बिंदीदार रेखाएं बनाने की अनुमति देते हैं।

#### प्रश्न: लाइन ऑब्जेक्ट जोड़ने के बाद मैं पीडीएफ फाइल को कैसे सहेज सकता हूं?

 उ: लाइन ऑब्जेक्ट जोड़ने के बाद, आप परिणामी पीडीएफ फाइल को इसका उपयोग करके सहेज सकते हैं`doc.Save(dataDir + "AddLineObject_out.pdf");` दिए गए स्रोत कोड में पंक्ति।

#### प्रश्न: क्या कोई नमूना स्रोत कोड उपलब्ध है?

उत्तर: हां, ट्यूटोरियल में एक नमूना स्रोत कोड शामिल है जिसे आप वर्णित चरणों को लागू करने के लिए संदर्भित कर सकते हैं।