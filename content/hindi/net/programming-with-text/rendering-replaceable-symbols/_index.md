---
title: पीडीएफ फाइल में प्रतिस्थापन योग्य प्रतीकों का प्रतिपादन
linktitle: पीडीएफ फाइल में प्रतिस्थापन योग्य प्रतीकों का प्रतिपादन
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में प्रतिस्थापन योग्य प्रतीकों को प्रस्तुत करना सीखें।
type: docs
weight: 310
url: /hi/net/programming-with-text/rendering-replaceable-symbols/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF फ़ाइल में प्रतिस्थापन योग्य प्रतीकों को कैसे प्रस्तुत किया जाए। हम PDF बनाने, न्यूलाइन मार्कर के साथ टेक्स्ट फ़्रैगमेंट जोड़ने, टेक्स्ट प्रॉपर्टी सेट करने, टेक्स्ट की स्थिति निर्धारित करने और दिए गए C# स्रोत कोड का उपयोग करके PDF को सहेजने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आप जेनरेट की गई पीडीएफ फाइल को सेव करना चाहते हैं।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपने इच्छित निर्देशिका के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक पीडीएफ दस्तावेज़ और पेज बनाएँ

 इसके बाद, हम एक नया पीडीएफ दस्तावेज़ बनाते हैं और इसमें एक पृष्ठ जोड़ते हैं`Document` वर्ग और`Page` Aspose.PDF लाइब्रेरी से क्लास.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## चरण 3: न्यूलाइन मार्कर के साथ टेक्स्ट फ़्रैगमेंट जोड़ें

 हम एक बनाते हैं`TextFragment` ऑब्जेक्ट और उसके पाठ को न्यूलाइन मार्कर शामिल करने के लिए सेट करें (`Environment.NewLine`) का उपयोग पाठ की एकाधिक पंक्तियों को दर्शाने के लिए करें।

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## चरण 4: टेक्स्ट फ़्रैगमेंट गुण सेट करें

यदि हम चाहें तो पाठ खंड के लिए विभिन्न गुण निर्धारित कर सकते हैं, जैसे फ़ॉन्ट आकार, फ़ॉन्ट, पृष्ठभूमि रंग और अग्रभूमि रंग।

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## चरण 5: टेक्स्ट पैराग्राफ़ और स्थिति बनाएँ

 हम एक बनाते हैं`TextParagraph` ऑब्जेक्ट को चुनें, पैराग्राफ में टेक्स्ट अंश जोड़ें, और पृष्ठ पर पैराग्राफ की स्थिति निर्धारित करें।

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## चरण 6: पृष्ठ पर टेक्स्ट पैराग्राफ़ जोड़ें

 हम एक बनाते हैं`TextBuilder` पृष्ठ के साथ ऑब्जेक्ट जोड़ें और टेक्स्ट पैराग्राफ को टेक्स्ट बिल्डर में जोड़ें।

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## चरण 7: पीडीएफ दस्तावेज़ सहेजें

अंत में, हम पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके प्रतिस्थापन योग्य प्रतीकों को प्रस्तुत करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// आवश्यक न्यूलाइन मार्कर वाले पाठ के साथ नया TextFragment आरंभ करें
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// यदि आवश्यक हो तो पाठ खंड गुण सेट करें
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// टेक्स्टपैराग्राफ ऑब्जेक्ट बनाएँ
TextParagraph par = new TextParagraph();
// पैराग्राफ़ में नया टेक्स्टफ़्रेगमेंट जोड़ें
par.AppendLine(textFragment);
// पैराग्राफ़ स्थिति सेट करें
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// TextBuilder ऑब्जेक्ट बनाएँ
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// TextBuilder का उपयोग करके TextParagraph जोड़ें
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में प्रतिस्थापन योग्य प्रतीकों को कैसे प्रस्तुत किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक PDF बना सकते हैं, न्यूलाइन मार्कर के साथ टेक्स्ट जोड़ सकते हैं, टेक्स्ट गुण सेट कर सकते हैं, पृष्ठ पर टेक्स्ट की स्थिति निर्धारित कर सकते हैं और PDF को सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में प्रतिस्थापन योग्य प्रतीकों का प्रतिपादन" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "पीडीएफ फाइल में प्रतिस्थापन योग्य प्रतीकों को प्रस्तुत करना" ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके एक पीडीएफ दस्तावेज़ कैसे बनाया जाए जिसमें प्रतिस्थापन योग्य प्रतीक शामिल हों। इन प्रतीकों को बहु-पंक्ति सामग्री बनाने के लिए न्यूलाइन मार्करों के साथ पाठ अंशों के रूप में दर्शाया जाता है।

#### प्रश्न: मैं PDF दस्तावेज़ में प्रतिस्थापन योग्य प्रतीकों को क्यों प्रस्तुत करना चाहूंगा?

उत्तर: प्रतिस्थापन योग्य प्रतीकों को प्रस्तुत करना तब उपयोगी होता है जब आपको गतिशील रूप से PDF सामग्री उत्पन्न करने की आवश्यकता होती है जिसमें परिवर्तनशील या उपयोगकर्ता-विशिष्ट जानकारी शामिल होती है। ये प्रतीक प्लेसहोल्डर के रूप में कार्य करते हैं जिन्हें रनटाइम के दौरान वास्तविक डेटा से बदला जा सकता है, जैसे कि फ़ॉर्म फ़ील्ड मान या वैयक्तिकृत विवरण।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे स्थापित करूँ?

उत्तर: दस्तावेज़ निर्देशिका सेट अप करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका का पथ वाला वेरिएबल जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं।

#### प्रश्न: मैं Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ में प्रतिस्थापन योग्य प्रतीकों को कैसे प्रस्तुत करूं?

उत्तर: ट्यूटोरियल आपको चरण दर चरण प्रक्रिया के माध्यम से मार्गदर्शन करता है:

1.  का उपयोग करके एक नया पीडीएफ दस्तावेज़ बनाएं`Document` कक्षा।
2.  दस्तावेज़ में पृष्ठ जोड़ने के लिए निम्न का उपयोग करें:`Page` कक्षा।
3.  एक बनाने के`TextFragment` न्यूलाइन मार्कर वाला ऑब्जेक्ट (`Environment.NewLine`) का उपयोग बहु-पंक्ति सामग्री को दर्शाने के लिए किया जाता है।
4. पाठ खंड के गुणधर्मों जैसे फ़ॉन्ट आकार, फ़ॉन्ट, पृष्ठभूमि रंग और अग्रभूमि रंग को अनुकूलित करें।
5.  एक बनाने के`TextParagraph` ऑब्जेक्ट पर क्लिक करें, उसमें टेक्स्ट अंश जोड़ें, तथा पृष्ठ पर पैराग्राफ की स्थिति निर्धारित करें।
6.  एक बनाने के`TextBuilder` पृष्ठ के साथ ऑब्जेक्ट जोड़ें और उसमें पाठ पैराग्राफ जोड़ें।
7. पीडीएफ दस्तावेज़ सहेजें.

#### प्रश्न: न्यूलाइन मार्करों का उपयोग करने का उद्देश्य क्या है?`Environment.NewLine`) in the text fragment?

 उत्तर: न्यूलाइन मार्कर का उपयोग एकल टेक्स्ट फ़्रैगमेंट में बहु-पंक्ति सामग्री बनाने के लिए किया जाता है।`Environment.NewLine`आप यह इंगित कर सकते हैं कि पाठ में पंक्ति विराम कहाँ होना चाहिए।

#### प्रश्न: क्या मैं प्रतिस्थापन योग्य प्रतीकों के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हां, आप टेक्स्ट फ़्रैगमेंट के विभिन्न गुणों को अनुकूलित कर सकते हैं, जैसे फ़ॉन्ट आकार, फ़ॉन्ट, पृष्ठभूमि रंग और अग्रभूमि रंग। ये गुण PDF दस्तावेज़ में प्रतिस्थापन योग्य प्रतीकों की दृश्य उपस्थिति निर्धारित करते हैं।

#### प्रश्न: मैं पृष्ठ पर पाठ की स्थिति कैसे निर्दिष्ट करूँ?

 उत्तर: आप टेक्स्ट की स्थिति निर्धारित करने के लिए एक टेक्स्ट बॉक्स बना सकते हैं।`TextParagraph` वस्तु और का उपयोग कर`Position` पृष्ठ पर X और Y निर्देशांक निर्दिष्ट करने के लिए गुण, जहां पैराग्राफ़ को रखा जाना चाहिए।

#### प्रश्न: दिए गए कोड को निष्पादित करने का अपेक्षित परिणाम क्या है?

उत्तर: ट्यूटोरियल का पालन करके और दिए गए C# कोड को चलाकर, आप एक PDF दस्तावेज़ बनाएँगे जिसमें प्रतिस्थापन योग्य प्रतीक शामिल होंगे। प्रतिस्थापन योग्य प्रतीकों को न्यूलाइन मार्कर और अनुकूलित गुणों के साथ पाठ अंशों के रूप में दर्शाया जाएगा।

#### प्रश्न: क्या मैं व्यक्तिगत PDF दस्तावेज़ों को गतिशील रूप से तैयार करने के लिए इस दृष्टिकोण का उपयोग कर सकता हूँ?

उत्तर: हां, यह दृष्टिकोण व्यक्तिगत जानकारी के साथ गतिशील रूप से पीडीएफ दस्तावेज़ बनाने के लिए उपयुक्त है। बदले जा सकने वाले प्रतीकों को वास्तविक डेटा से बदलकर, आप प्रत्येक उपयोगकर्ता या परिदृश्य के लिए अनुकूलित पीडीएफ सामग्री बना सकते हैं।