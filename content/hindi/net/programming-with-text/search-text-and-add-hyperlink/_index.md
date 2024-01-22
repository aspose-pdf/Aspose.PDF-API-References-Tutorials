---
title: टेक्स्ट खोजें और हाइपरलिंक जोड़ें
linktitle: टेक्स्ट खोजें और हाइपरलिंक जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि पीडीएफ में टेक्स्ट कैसे खोजें, पाए गए टेक्स्ट में हाइपरलिंक कैसे जोड़ें, और .NET के लिए Aspose.PDF का उपयोग करके संशोधित दस्तावेज़ को सहेजें।
type: docs
weight: 450
url: /hi/net/programming-with-text/search-text-and-add-hyperlink/
---
यह ट्यूटोरियल बताता है कि पीडीएफ दस्तावेज़ में विशिष्ट पाठ की खोज करने, पाए गए पाठ में हाइपरलिंक जोड़ने और संशोधित दस्तावेज़ को सहेजने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। प्रदान किया गया C# स्रोत कोड चरण दर चरण प्रक्रिया को प्रदर्शित करता है।

## आवश्यक शर्तें

ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित। आप इसे Aspose वेबसाइट से प्राप्त कर सकते हैं या इसे अपने प्रोजेक्ट में इंस्टॉल करने के लिए NuGet का उपयोग कर सकते हैं।

## चरण 1: प्रोजेक्ट सेट करें

अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाकर शुरुआत करें और .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें।

## चरण 2: आवश्यक नामस्थान आयात करें

आवश्यक नामस्थान आयात करने के लिए अपनी C# फ़ाइल की शुरुआत में निम्नलिखित निर्देशों का उपयोग करके जोड़ें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## चरण 3: दस्तावेज़ निर्देशिका के लिए पथ सेट करें

 का उपयोग करके अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करें`dataDir` चर:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 4: एक टेक्स्टफ्रैगमेंटएब्जॉर्बर बनाएं

 एक बनाने के`TextFragmentAbsorber` इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए ऑब्जेक्ट:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 प्रतिस्थापित करें`"\\d{4}-\\d{4}"` अपने वांछित नियमित अभिव्यक्ति पैटर्न के साथ।

## चरण 5: रेगुलर एक्सप्रेशन खोज सक्षम करें

 सेट करके रेगुलर एक्सप्रेशन खोज सक्षम करें`TextSearchOptions` अवशोषक की संपत्ति:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## चरण 6: पीडीएफ दस्तावेज़ खोलें और बाइंड करें

 एक बनाने के`PdfContentEditor` ऑब्जेक्ट करें और इसे स्रोत पीडीएफ फाइल से बांधें:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 प्रतिस्थापित करें`"SearchRegularExpressionPage.pdf"` आपकी पीडीएफ फाइल के वास्तविक नाम के साथ।

## चरण 7: पृष्ठ के लिए अवशोषक स्वीकार करें

दस्तावेज़ के वांछित पृष्ठ के लिए अवशोषक स्वीकार करें:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 प्रतिस्थापित करें`1` वांछित पृष्ठ संख्या के साथ.

## चरण 8: पाए गए टेक्स्ट में हाइपरलिंक जोड़ें

पुनर्प्राप्त पाठ अंशों के माध्यम से लूप करें और उनमें हाइपरलिंक जोड़ें:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // पाठ खंड की स्थिति के आधार पर एक आयत बनाएं
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //आयत में एक वेब लिंक जोड़ें
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 प्रतिस्थापित करें`"http://www.aspose.com"` वांछित हाइपरलिंक यूआरएल के साथ.

## चरण 9: संशोधित दस्तावेज़ को सहेजें और बंद करें

संशोधित दस्तावेज़ सहेजें और संपादक बंद करें:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 प्रतिस्थापित करना सुनिश्चित करें`"SearchTextAndAddHyperlink_out.pdf"` वांछित आउटपुट फ़ाइल नाम के साथ।

### .NET के लिए Aspose.PDF का उपयोग करके टेक्स्ट खोजने और हाइपरलिंक जोड़ने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// इनपुट खोज वाक्यांश के सभी उदाहरण खोजने के लिए अवशोषक ऑब्जेक्ट बनाएं
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// रेगुलर एक्सप्रेशन खोज सक्षम करें
absorber.TextSearchOptions = new TextSearchOptions(true);
// दस्तावेज़ खोलें
PdfContentEditor editor = new PdfContentEditor();
// स्रोत पीडीएफ फाइल को बाइंड करें
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// पृष्ठ के लिए अवशोषक स्वीकार करें
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// टुकड़ों के माध्यम से लूप करें
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, नीला, एक्शननाम);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि पीडीएफ दस्तावेज़ में विशिष्ट पाठ की खोज कैसे करें, पाए गए पाठ में हाइपरलिंक कैसे जोड़ें, और .NET के लिए Aspose.PDF का उपयोग करके संशोधित दस्तावेज़ को कैसे सहेजें। इस ट्यूटोरियल में प्रोजेक्ट स्थापित करने से लेकर आवश्यक कार्रवाई करने तक चरण-दर-चरण मार्गदर्शिका प्रदान की गई। अब आप टेक्स्ट में हेरफेर करने और पीडीएफ फाइलों में हाइपरलिंक जोड़ने के लिए इस कोड को अपने सी# प्रोजेक्ट में शामिल कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "टेक्स्ट खोजें और हाइपरलिंक जोड़ें" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पाठ खोजें और हाइपरलिंक जोड़ें" ट्यूटोरियल का उद्देश्य यह प्रदर्शित करना है कि पीडीएफ दस्तावेज़ के भीतर विशिष्ट पाठ की खोज करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें, पाए गए पाठ में हाइपरलिंक जोड़ें और फिर संशोधित दस्तावेज़ को सहेजें। चरण-दर-चरण प्रक्रिया को समझाने के लिए ट्यूटोरियल एक व्यापक मार्गदर्शिका और C# कोड नमूने प्रदान करता है।

#### प्रश्न: यह ट्यूटोरियल पीडीएफ दस्तावेज़ में विशिष्ट पाठ में हाइपरलिंक जोड़ने में कैसे मदद करता है?

उ: यह ट्यूटोरियल आपको पीडीएफ दस्तावेज़ में विशिष्ट पाठ का पता लगाने, पहचाने गए पाठ पर हाइपरलिंक लागू करने और संशोधित पीडीएफ को सहेजने के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया में मार्गदर्शन करता है। इसमें प्रोजेक्ट स्थापित करना, दस्तावेज़ लोड करना, नियमित अभिव्यक्ति खोज सक्षम करना और पाए गए टेक्स्ट में हाइपरलिंक जोड़ना जैसे आवश्यक चरण शामिल हैं।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए किन पूर्वावश्यकताओं की आवश्यकता है?

उत्तर: शुरू करने से पहले, आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ होनी चाहिए। इसके अतिरिक्त, आपको .NET लाइब्रेरी के लिए Aspose.PDF इंस्टॉल करना होगा, जिसे Aspose वेबसाइट से प्राप्त किया जा सकता है या अपने प्रोजेक्ट में NuGet का उपयोग करके इंस्टॉल किया जा सकता है।

#### प्रश्न: मैं इस ट्यूटोरियल का अनुसरण करने के लिए अपना प्रोजेक्ट कैसे सेट करूँ?

उ: अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया सी# प्रोजेक्ट बनाकर शुरुआत करें। फिर, .NET लाइब्रेरी के लिए Aspose.PDF का एक संदर्भ जोड़ें, जो आपको अपने प्रोजेक्ट में लाइब्रेरी की क्षमताओं का उपयोग करने में सक्षम करेगा।

#### प्रश्न: क्या मैं इस ट्यूटोरियल का उपयोग करके विशिष्ट पाठ में हाइपरलिंक जोड़ सकता हूँ?

उत्तर: हाँ, यह ट्यूटोरियल विशेष रूप से पीडीएफ दस्तावेज़ में विशिष्ट पाठ में हाइपरलिंक जोड़ने पर केंद्रित है। यह दर्शाता है कि नियमित अभिव्यक्तियों का उपयोग करके वांछित पाठ को कैसे ढूंढें और निकालें, पाठ के टुकड़ों से जुड़े हाइपरलिंक बनाएं और संशोधित पीडीएफ को सहेजें।

#### प्रश्न: मैं उस पाठ को कैसे परिभाषित करूं जिसे मैं खोजना चाहता हूं और उसमें हाइपरलिंक कैसे जोड़ूं?

 उ: उस पाठ को निर्दिष्ट करने के लिए जिसे आप खोजना चाहते हैं और उसमें हाइपरलिंक जोड़ना चाहते हैं, एक बनाएं`TextFragmentAbsorber` ऑब्जेक्ट बनाएं और उसका पैटर्न सेट करें`Text` पैरामीटर. डिफ़ॉल्ट पैटर्न बदलें`"\\d{4}-\\d{4}"` अपने वांछित नियमित अभिव्यक्ति पैटर्न के साथ ट्यूटोरियल के कोड में।

#### प्रश्न: मैं टेक्स्ट के लिए रेगुलर एक्सप्रेशन खोज कैसे सक्षम कर सकता हूं?

 ए: रेगुलर एक्सप्रेशन खोज को बनाकर सक्षम किया गया है`TextSearchOptions` ऑब्जेक्ट और उसका मान सेट करना`true` . इस ऑब्जेक्ट को असाइन करें`TextSearchOptions` की संपत्ति`TextFragmentAbsorber` उदाहरण। यह सुनिश्चित करता है कि पाठ खोज के दौरान नियमित अभिव्यक्ति पैटर्न लागू किया जाता है।

#### प्रश्न: मैं पाए गए टेक्स्ट में हाइपरलिंक कैसे जोड़ूं?

 ए: का उपयोग करके पाठ के टुकड़ों की पहचान करने के बाद`TextFragmentAbsorber` , ट्यूटोरियल इन अंशों के माध्यम से पुनरावृत्त करने के लिए एक लूप प्रदान करता है। प्रत्येक पाठ खंड के लिए, ट्यूटोरियल दर्शाता है कि पाठ का रंग नीला कैसे सेट करें और इसका उपयोग करके हाइपरलिंक कैसे बनाएं`CreateWebLink` तरीका।

#### प्रश्न: संशोधित पीडीएफ को हाइपरलिंक के साथ सहेजने के लिए क्या कदम हैं?

 उ: वांछित पाठ अंशों में हाइपरलिंक जोड़ने के बाद, इसका उपयोग करें`PdfContentEditor` संशोधित दस्तावेज़ को सहेजने के लिए क्लास। ट्यूटोरियल का नमूना कोड दिखाता है कि संपादित पीडीएफ को कैसे सहेजना है, संपादक को बंद करना है और एक सफलता संदेश प्रदर्शित करना है।