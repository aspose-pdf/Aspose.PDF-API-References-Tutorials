---
title: दस्तावेज़ विंडो प्राप्त करें
linktitle: दस्तावेज़ विंडो प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: पीडीएफ दस्तावेज़ की विंडो गुणों के बारे में जानकारी प्राप्त करने के लिए .NET के लिए Aspose.PDF की GetDocumentWindow सुविधा का उपयोग करना सीखें।
type: docs
weight: 170
url: /hi/net/programming-with-document/getdocumentwindow/
---
 .NET के लिए Aspose.PDF एक शक्तिशाली PDF हेरफेर लाइब्रेरी है जो डेवलपर्स को अपने .NET अनुप्रयोगों में PDF फ़ाइलें बनाने, संपादित करने और परिवर्तित करने की अनुमति देता है। इस लाइब्रेरी द्वारा दी जाने वाली सुविधाओं में से एक दस्तावेज़ की विंडो गुणों के बारे में जानकारी पुनर्प्राप्त करने की क्षमता है। यह ट्यूटोरियल आपको इसके उपयोग के चरणों के बारे में मार्गदर्शन करेगा`GetDocumentWindow` पीडीएफ दस्तावेज़ की विंडो गुणों के बारे में जानकारी प्राप्त करने के लिए .NET के लिए Aspose.PDF की सुविधा।

## चरण 1: .NET के लिए Aspose.PDF इंस्टॉल करें

 अपने .NET अनुप्रयोगों में .NET के लिए Aspose.PDF का उपयोग करने के लिए, आपको पहले लाइब्रेरी स्थापित करनी होगी। आप लाइब्रेरी का नवीनतम संस्करण यहां से डाउनलोड कर सकते हैं[.NET डाउनलोड पेज के लिए Aspose.PDF](https://releases.aspose.com/pdf/net).

एक बार जब आप लाइब्रेरी डाउनलोड कर लें, तो ज़िप फ़ाइल की सामग्री को अपने कंप्यूटर पर एक फ़ोल्डर में निकालें। फिर आपको अपने .NET प्रोजेक्ट में .NET DLL के लिए Aspose.PDF का एक संदर्भ जोड़ना होगा।

## चरण 2: पीडीएफ दस्तावेज़ लोड करें

एक बार जब आप .NET के लिए Aspose.PDF इंस्टॉल कर लेते हैं और अपने .NET प्रोजेक्ट में DLL का संदर्भ जोड़ लेते हैं, तो आप इसका उपयोग शुरू कर सकते हैं`GetDocumentWindow` पीडीएफ दस्तावेज़ की विंडो गुणों के बारे में जानकारी प्राप्त करने की सुविधा।

इस सुविधा का उपयोग करने में पहला कदम उस पीडीएफ दस्तावेज़ को लोड करना है जिसके बारे में आप जानकारी पुनः प्राप्त करना चाहते हैं। ऐसा करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```csharp
// पीडीएफ दस्तावेज़ का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

//पीडीएफ दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 उपरोक्त कोड में, प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के पथ के साथ जहां आपका पीडीएफ दस्तावेज़ स्थित है। यह कोड पीडीएफ दस्तावेज़ को एक में लोड करेगा`Document` ऑब्जेक्ट, जिसका उपयोग आप दस्तावेज़ की विंडो गुणों के बारे में जानकारी प्राप्त करने के लिए कर सकते हैं।

## चरण 3: दस्तावेज़ की विंडो गुण पुनः प्राप्त करें

पीडीएफ दस्तावेज़ की विंडो गुणों के बारे में जानकारी प्राप्त करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```csharp
// दस्तावेज़ की विंडो गुण पुनः प्राप्त करें
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

उपरोक्त कोड में, प्रत्येक पंक्ति पीडीएफ दस्तावेज़ की एक अलग विंडो प्रॉपर्टी पुनर्प्राप्त करती है और इसे कंसोल पर आउटपुट करती है। आप केवल उन्हीं संपत्तियों को पुनः प्राप्त करने के लिए इस कोड को अनुकूलित कर सकते हैं जिनमें आपकी रुचि है।

### .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल की दस्तावेज़ विंडो प्राप्त करने के लिए उदाहरण स्रोत कोड 

 का उपयोग करके पीडीएफ दस्तावेज़ की विंडो गुणों को पुनः प्राप्त करने के लिए पूर्ण स्रोत कोड यहां दिया गया है`GetDocumentWindow` .NET के लिए Aspose.PDF की सुविधा:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// विभिन्न दस्तावेज़ गुण प्राप्त करें
// दस्तावेज़ की विंडो की स्थिति - डिफ़ॉल्ट: ग़लत
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// प्रमुख पढ़ने का क्रम; पेज की स्थिति निर्धारित करता है
// जब साथ-साथ प्रदर्शित किया जाता है - डिफ़ॉल्ट: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// क्या विंडो के टाइटल बार में दस्तावेज़ का शीर्षक प्रदर्शित होना चाहिए
// यदि गलत है, तो शीर्षक बार पीडीएफ फ़ाइल नाम प्रदर्शित करता है - डिफ़ॉल्ट: गलत
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// दस्तावेज़ की विंडो का आकार उसके आकार के अनुसार बदलना है या नहीं
// पहला प्रदर्शित पृष्ठ - डिफ़ॉल्ट: गलत
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// व्यूअर एप्लिकेशन के मेनू बार को छिपाना है या नहीं - डिफ़ॉल्ट: गलत
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//व्यूअर एप्लिकेशन के टूल बार को छिपाना है या नहीं - डिफ़ॉल्ट: गलत
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// स्क्रॉल बार जैसे यूआई तत्वों को छिपाना है या नहीं
// और केवल पृष्ठ सामग्री को प्रदर्शित छोड़ रहा है - डिफ़ॉल्ट: गलत
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// दस्तावेज़ का पृष्ठ मोड. फ़ुल-स्क्रीन मोड से बाहर निकलने पर दस्तावेज़ कैसे प्रदर्शित करें।
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// पेज लेआउट यानी सिंगल पेज, एक कॉलम
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// खोले जाने पर दस्तावेज़ कैसे प्रदर्शित होना चाहिए
// यानी थंबनेल दिखाएं, फ़ुल-स्क्रीन, अटैचमेंट पैनल दिखाएं
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि पीडीएफ दस्तावेज़ की विंडो गुणों के बारे में जानकारी प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। एक पीडीएफ दस्तावेज़ को लोड करके और उसकी विंडो गुणों तक पहुंच कर, आप इस बारे में जानकारी इकट्ठा कर सकते हैं कि व्यूअर एप्लिकेशन में खोले जाने पर दस्तावेज़ को कैसे प्रदर्शित किया जाना चाहिए। .NET के लिए Aspose.PDF प्रोग्रामेटिक रूप से पीडीएफ फाइलों के साथ काम करने के लिए सुविधाओं का एक शक्तिशाली सेट प्रदान करता है, जिससे यह .NET अनुप्रयोगों में पीडीएफ हेरफेर के लिए एक मूल्यवान उपकरण बन जाता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ की विंडो गुणों को पुनः प्राप्त करने का उद्देश्य क्या है?

उ: पीडीएफ दस्तावेज़ की विंडो गुणों को पुनः प्राप्त करने से आप इस बारे में जानकारी एकत्र कर सकते हैं कि व्यूअर एप्लिकेशन में खोले जाने पर पीडीएफ दस्तावेज़ को कैसे प्रदर्शित किया जाना चाहिए। ये गुण विभिन्न पहलुओं जैसे विंडो स्थिति, डिस्प्ले मोड और यूआई तत्वों की दृश्यता को नियंत्रित करते हैं।

#### प्रश्न: मैं अपने .NET प्रोजेक्ट में .NET के लिए Aspose.PDF कैसे स्थापित कर सकता हूं?

 उ: .NET के लिए Aspose.PDF इंस्टॉल करने के लिए, आपको लाइब्रेरी डाउनलोड करनी होगी[.NET डाउनलोड पेज के लिए Aspose.PDF](https://releases.aspose.com/pdf/net). डाउनलोड करने के बाद, ज़िप फ़ाइल की सामग्री निकालें और अपने .NET प्रोजेक्ट में .NET DLL के लिए Aspose.PDF का संदर्भ जोड़ें।

#### प्रश्न: क्या मैं केवल विशिष्ट विंडो गुणों को पुनः प्राप्त करने के लिए कोड को अनुकूलित कर सकता हूँ?

उ: हाँ, आप उन पंक्तियों पर टिप्पणी करके विशिष्ट विंडो गुणों को पुनः प्राप्त करने के लिए कोड को अनुकूलित कर सकते हैं जिनकी आपको आवश्यकता नहीं है। कोड की प्रत्येक पंक्ति एक विशिष्ट विंडो प्रॉपर्टी से मेल खाती है, इसलिए आप अपनी आवश्यकताओं के आधार पर प्रॉपर्टी को शामिल या बाहर कर सकते हैं।

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके मैं किस प्रकार की विंडो संपत्तियों को पुनः प्राप्त कर सकता हूं?

उ: .NET के लिए Aspose.PDF का उपयोग करके, आप पीडीएफ दस्तावेज़ के विभिन्न विंडो गुणों को पुनः प्राप्त कर सकते हैं, जिसमें विंडो को केंद्रित करना, पेज लेआउट सेट करना, टूलबार और मेनू बार के प्रदर्शन को नियंत्रित करना और बहुत कुछ शामिल है।