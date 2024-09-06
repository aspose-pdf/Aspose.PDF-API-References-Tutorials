---
title: छवि को XImage संग्रह में संग्रहीत करें
linktitle: छवि को XImage संग्रह में संग्रहीत करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके XImage संग्रह में छवि संग्रहीत करने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 290
url: /hi/net/programming-with-images/store-image-in-ximage-collection/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके XImage संग्रह में छवि संग्रहीत करने का तरीका बताएँगे। इस ऑपरेशन को आसानी से करने के लिए इन चरणों का पालन करें।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या कोई अन्य विकास वातावरण स्थापित और कॉन्फ़िगर किया गया।
- C# प्रोग्रामिंग भाषा का मूलभूत ज्ञान।
- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है। आप इसे Aspose की आधिकारिक वेबसाइट से डाउनलोड कर सकते हैं।

## चरण 1: पीडीएफ दस्तावेज़ आरंभीकरण

आरंभ करने के लिए, एक नया PDF दस्तावेज़ आरंभ करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//दस्तावेज़ आरंभ करें
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## चरण 2: छवि को XImage संग्रह में जोड़ना

इसके बाद, हम छवि को PDF दस्तावेज़ के XImage संग्रह में जोड़ेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

छवि स्रोत फ़ाइल का सही पथ प्रदान करना सुनिश्चित करें।

## चरण 3: पृष्ठ पर छवि का स्थान

अब आइए छवि को PDF दस्तावेज़ के पृष्ठ पर रखें। निम्नलिखित कोड का उपयोग करें:

```csharp
page. Contents. Add(new GSave());

// निर्देशांक सेट करें
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// ConcatenateMatrix ऑपरेटर का उपयोग करके: परिभाषित करें कि छवि को कैसे रखा जाना चाहिए
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

इससे छवि पृष्ठ पर निर्दिष्ट निर्देशांक पर आ जाएगी।

## चरण 4: पीडीएफ दस्तावेज़ को सहेजना

अंत में, हम अपडेट किए गए PDF दस्तावेज़ को सेव करेंगे। निम्नलिखित कोड का उपयोग करें:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

अंतिम PDF दस्तावेज़ के लिए वांछित पथ और फ़ाइल नाम प्रदान करना सुनिश्चित करें।

### .NET के लिए Aspose.PDF का उपयोग करके XImage संग्रह में छवि संग्रहीत करने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ आरंभ करें
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// निर्देशांक सेट करें
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// ConcatenateMatrix (कॉन्कैटेनेट मैट्रिक्स) ऑपरेटर का उपयोग करना: परिभाषित करता है कि छवि को कैसे रखा जाना चाहिए
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके XImage संग्रह में सफलतापूर्वक एक छवि संग्रहीत की है। अब आप PDF फ़ाइलों में छवियों को हेरफेर करने और वैयक्तिकृत करने के लिए इस विधि को अपनी खुद की परियोजनाओं पर लागू कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके XImage संग्रह में छवि संग्रहीत करने का उद्देश्य क्या है?

उत्तर: XImage संग्रह में छवि संग्रहीत करने से आप PDF दस्तावेज़ में छवियों को कुशलतापूर्वक प्रबंधित और उपयोग कर सकते हैं। यह दृष्टिकोण आपको विशिष्ट पृष्ठों पर रखने से पहले छवियों में हेरफेर, अनुकूलन और वैयक्तिकृत करने में सक्षम बनाता है।

#### प्रश्न: XImage संग्रह में छवि संग्रहीत करना, PDF पृष्ठ पर सीधे छवि रखने से किस प्रकार भिन्न है?

उत्तर: XImage संग्रह में छवि संग्रहीत करने से छवियों को प्रबंधित करने का अधिक व्यवस्थित और पुनः उपयोग करने योग्य तरीका मिलता है। किसी छवि को सीधे पृष्ठ पर रखने के बजाय, आप उसे संग्रह में संग्रहीत करते हैं और फिर ज़रूरत पड़ने पर उसे नाम से संदर्भित कर सकते हैं, जिससे प्रबंधन और संशोधन आसान हो जाता है।

#### प्रश्न: क्या मैं एक ही PDF दस्तावेज़ में XImage संग्रह में एकाधिक छवियाँ जोड़ सकता हूँ?

उत्तर: हां, आप एक ही PDF दस्तावेज़ में XImage संग्रह में कई छवियाँ जोड़ सकते हैं। संग्रह में प्रत्येक छवि को एक अद्वितीय नाम दिया गया है, जिसका उपयोग छवियों को अलग-अलग पृष्ठों पर संदर्भित करने और रखने के लिए किया जा सकता है।

#### प्रश्न: XImage संग्रह से PDF पृष्ठ पर छवि रखते समय मैं उसकी स्थिति और आकार कैसे निर्दिष्ट करूँ?

उत्तर: छवि की स्थिति और आकार निर्दिष्ट करने के लिए, आपको एक आयत और एक मैट्रिक्स परिवर्तन को परिभाषित करना होगा। आयत छवि की सीमाओं को परिभाषित करता है, और मैट्रिक्स परिवर्तन निर्दिष्ट करता है कि छवि को उस आयत के भीतर कैसे रखा जाना चाहिए।

####  प्रश्न: इसका उद्देश्य क्या है?`GSave()` and `GRestore()` operators in the code for placing the image?

 उत्तर:`GSave()` और`GRestore()` ऑपरेटरों का उपयोग पीडीएफ पेज की ग्राफ़िक्स स्थिति को सहेजने और पुनर्स्थापित करने के लिए किया जाता है। यह सुनिश्चित करता है कि पेज पर किए गए ऑपरेशन, जैसे कि छवि को रखना, छवि रखने के बाद पेज की स्थिति को प्रभावित नहीं करते हैं।

#### प्रश्न: क्या मैं XImage संग्रह में संग्रहीत छवियों पर अतिरिक्त संशोधन या रूपांतरण लागू कर सकता हूं?

उत्तर: हाँ, आप XImage संग्रह में संग्रहीत छवियों पर विभिन्न संशोधन और परिवर्तन लागू कर सकते हैं। आप .NET के लिए Aspose.PDF द्वारा प्रदान किए गए उचित संचालन और तकनीकों का उपयोग करके घुमा सकते हैं, स्केल कर सकते हैं, क्रॉप कर सकते हैं और अन्य परिवर्तन कर सकते हैं।

#### प्रश्न: मैं PDF दस्तावेज़ के XImage संग्रह में छवियों को संग्रहीत करने और रखने के लिए इस पद्धति को अपनी परियोजनाओं में कैसे एकीकृत कर सकता हूं?

उत्तर: इस विधि को एकीकृत करने के लिए, उल्लिखित चरणों का पालन करें और अपने प्रोजेक्ट की आवश्यकताओं को पूरा करने के लिए कोड को संशोधित करें। आप छवियों को संग्रहीत और प्रबंधित करने के लिए XImage संग्रह का उपयोग कर सकते हैं, फिर उन्हें निर्दिष्ट निर्देशांक और परिवर्तनों का उपयोग करके विशिष्ट पृष्ठों पर रख सकते हैं।

#### प्रश्न: .NET के लिए Aspose.PDF में XImage संग्रह के साथ काम करते समय क्या कोई विचार या सीमाएँ हैं?

उत्तर: जबकि XImage संग्रह छवियों को प्रबंधित करने और हेरफेर करने का एक शक्तिशाली तरीका प्रदान करता है, मेमोरी उपयोग और छवियों पर किए गए संचालन की जटिलता जैसे कारकों पर विचार करना महत्वपूर्ण है। संग्रह का सावधानीपूर्वक प्रबंधन और संसाधनों का कुशल उपयोग करने की अनुशंसा की जाती है।

#### प्रश्न: क्या मैं XImage संग्रह में संग्रहीत छवियों को एकाधिक PDF दस्तावेज़ों में पुनः उपयोग कर सकता हूँ?

उत्तर: XImage संग्रह प्रत्येक PDF दस्तावेज़ के लिए विशिष्ट है और इसे क्रॉस-दस्तावेज़ पुनः उपयोग के लिए डिज़ाइन नहीं किया गया है। यदि आपको कई दस्तावेज़ों में छवियों का पुनः उपयोग करने की आवश्यकता है, तो आपको उन्हें प्रत्येक दस्तावेज़ के लिए अलग से संग्रहीत और प्रबंधित करना होगा।