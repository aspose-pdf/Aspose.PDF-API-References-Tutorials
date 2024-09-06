---
title: पेज पर XForm बनाएं
linktitle: पेज पर XForm बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF पृष्ठ पर XForm फ़ॉर्म बनाने के लिए चरण-दर-चरण मार्गदर्शिका। पृष्ठ पर फ़ॉर्म जोड़ें और उसे स्थान दें।
type: docs
weight: 10
url: /hi/net/programming-with-operators/draw-xform-on-page/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके किसी पृष्ठ पर XForm बनाने के तरीके के बारे में चरण-दर-चरण मार्गदर्शन प्रदान करेंगे। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, उनमें हेरफेर करने और उन्हें परिवर्तित करने की अनुमति देती है। Aspose.PDF द्वारा प्रदान किए गए ऑपरेटरों का उपयोग करके, आप किसी मौजूदा PDF पृष्ठ पर XForm फ़ॉर्म जोड़ और रख सकते हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. .NET फ्रेमवर्क के साथ स्थापित विजुअल स्टूडियो.
2. .NET के लिए Aspose.PDF लाइब्रेरी.

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, Visual Studio में एक नया प्रोजेक्ट बनाएँ और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। आप Aspose की आधिकारिक वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं और इसे अपनी मशीन पर इंस्टॉल कर सकते हैं।

## चरण 2: आवश्यक नामस्थान आयात करें

अपनी C# कोड फ़ाइल में, Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करें:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## चरण 3: फ़ाइल पथ सेट करना

पृष्ठभूमि छवि, इनपुट PDF फ़ाइल और आउटपुट PDF फ़ाइल के लिए फ़ाइल पथ परिभाषित करें:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

अपनी मशीन पर वास्तविक फ़ाइल पथ निर्दिष्ट करना सुनिश्चित करें।

## चरण 4: इनपुट पीडीएफ फाइल लोड करना

इनपुट पीडीएफ फाइल लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// निम्नलिखित कोड GSave/GRestore ऑपरेटर का उपयोग करता है
// कोड XForm को स्थान देने के लिए ContatenateMatrix ऑपरेटर का उपयोग करता है
// कोड पृष्ठ पर XForm बनाने के लिए Do ऑपरेटर का उपयोग करता है
// GSave/GRestore ऑपरेटर मौजूदा सामग्री को लपेटते हैं
//यह मौजूदा सामग्री के अंत में प्रारंभिक ग्राफ़िक्स स्थिति प्राप्त करने के लिए किया जाता है
// अन्यथा मौजूदा ऑपरेटरों की श्रृंखला के अंत में अवांछित परिवर्तन रह सकते हैं
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// नए आदेशों के बाद ग्राफ़िक्स स्थिति को उचित रूप से रीसेट करने के लिए GSave ऑपरेटर जोड़ें
pageContents. Add(new GSave());

// XForm बनाएं
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// छवि की चौड़ाई और ऊंचाई निर्धारित करें
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// छवि को स्ट्रीम में लोड करें
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// छवि को XForm संसाधन छवि संग्रह में जोड़ें
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Do ऑपरेटर का उपयोग करना: यह ऑपरेटर छवि बनाता है
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// XForm को निर्देशांक x=100 और y=500 पर रखें
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Do ऑपरेटर के साथ XForm बनाएं
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// XForm को निर्देशांक x=100 और y=300 पर रखें
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Do ऑपरेटर के साथ XForm बनाएं
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// GSave के बाद GRestore के साथ ग्राफ़िक्स स्थिति को पुनर्स्थापित करें
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

वास्तविक फ़ाइल पथ निर्दिष्ट करना सुनिश्चित करें और आवश्यकतानुसार पृष्ठ संख्या और XForm स्थिति समायोजित करें।

### .NET के लिए Aspose.PDF का उपयोग करके पेज पर XForm ड्रा करने के लिए नमूना स्रोत कोड
 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// नमूना दर्शाता है
	// GSave/GRestore ऑपरेटर का उपयोग
	// xForm को स्थान देने के लिए ContatenateMatrix ऑपरेटर का उपयोग
	//पृष्ठ पर xForm बनाने के लिए Do ऑपरेटर का उपयोग करें
	// GSave/GRestore ऑपरेटर युग्म के साथ मौजूदा सामग्री को लपेटें
	// यह मौजूदा सामग्री की प्रारंभिक ग्राफ़िक्स स्थिति प्राप्त करने के लिए है
	// अन्यथा मौजूदा ऑपरेटर श्रृंखला के अंत में कुछ अवांछनीय परिवर्तन रह सकते हैं
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// नए आदेशों के बाद ग्राफ़िक्स स्थिति को उचित रूप से साफ़ करने के लिए सेव ग्राफ़िक्स स्थिति ऑपरेटर जोड़ें
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm बनाएं
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// छवि की चौड़ाई और ऊंचाई निर्धारित करें
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// छवि को स्ट्रीम में लोड करें
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// XForm संसाधन के छवि संग्रह में छवि जोड़ें
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Do ऑपरेटर का उपयोग करना: यह ऑपरेटर छवि बनाता है
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// x=100 y=500 निर्देशांक पर स्थान फ़ॉर्म
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Do ऑपरेटर के साथ फॉर्म बनाएं
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// x=100 y=300 निर्देशांक पर स्थान फ़ॉर्म
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Do ऑपरेटर के साथ फॉर्म बनाएं
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// GSave के बाद GRestore के साथ ग्राफिक्स स्थिति को पुनर्स्थापित करें
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके PDF पेज पर XForm फ़ॉर्म कैसे बनाया जाता है। वर्णित चरणों का पालन करके, आप किसी मौजूदा पेज पर XForm फ़ॉर्म को जोड़ने और उसकी स्थिति निर्धारित करने में सक्षम होंगे, जिससे आपके PDF दस्तावेज़ों को अधिक लचीलापन मिलेगा।

### पृष्ठ पर XForm ड्रा के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.PDF में XForm क्या है?

उत्तर: XForm एक PDF दस्तावेज़ में एक पुन: प्रयोज्य ग्राफ़िकल ऑब्जेक्ट है। यह आपको जटिल ग्राफ़िक्स, इमेज या टेक्स्ट को परिभाषित करने और ड्रा करने की अनुमति देता है, जिसे अलग-अलग पेजों पर कई बार पुन: उपयोग किया जा सकता है।

#### प्रश्न: मैं Aspose.PDF के लिए आवश्यक नामस्थान कैसे आयात करूं?

 उत्तर: अपनी C# कोड फ़ाइल में, का उपयोग करें`using` Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करने का निर्देश:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### प्रश्न: GSave और GRestore ऑपरेटरों का उद्देश्य क्या है?

 उत्तर:`GSave` और`GRestore` Aspose.PDF में ऑपरेटर्स का उपयोग ग्राफ़िक्स स्थिति को सहेजने और पुनर्स्थापित करने के लिए किया जाता है। वे यह सुनिश्चित करने में मदद करते हैं कि सामग्री के एक भाग पर लागू किए गए परिवर्तन और सेटिंग बाद के भागों को प्रभावित न करें।

#### प्रश्न: मैं Aspose.PDF का उपयोग करके XForm कैसे परिभाषित करूं?

 उत्तर: XForm बनाने के लिए, का उपयोग करें`XForm.CreateNewForm` विधि और इसे में जोड़ें`Resources.Forms` किसी विशिष्ट पृष्ठ का संग्रह। फिर आप XForm में सामग्री जोड़ सकते हैं`Contents` संपत्ति।

#### प्रश्न: मैं XForm में छवि कैसे बना सकता हूँ?

उत्तर: छवि को स्ट्रीम में लोड करें और उसे जोड़ें`Resources.Images` XForm का संग्रह। का उपयोग करें`Do` XForm के भीतर ऑपरेटर`Contents` चित्र बनाने के लिए.

#### प्रश्न: मैं PDF पृष्ठ पर XForm को कैसे रखूं?

 उत्तर: किसी पृष्ठ पर XForm को रखने के लिए, का उपयोग करें`ConcatenateMatrix` पृष्ठ के अंदर ऑपरेटर`Contents`XForm के अनुवाद (स्थिति) और स्केलिंग को निर्दिष्ट करने के लिए मैट्रिक्स पैरामीटर्स को समायोजित करें।

#### प्रश्न: क्या मैं एक ही पृष्ठ पर एकाधिक XForms बना सकता हूँ?

 उत्तर: हां, आप सेटिंग समायोजित करके एक ही पृष्ठ पर कई XForms बना सकते हैं।`ConcatenateMatrix` प्रत्येक XForm को अलग-अलग निर्देशांकों पर स्थित करने के लिए पैरामीटर।

#### प्रश्न: क्या मैं XForm के निर्माण के बाद उसकी सामग्री को संशोधित कर सकता हूँ?

 उत्तर: हां, आप निर्माण के बाद XForm की सामग्री में अतिरिक्त ऑपरेटर जोड़कर उसे संशोधित कर सकते हैं।`Contents` संपत्ति।

#### प्रश्न: यदि मैं GSave और GRestore ऑपरेटर को छोड़ दूं तो क्या होगा?

उत्तर: GSave और GRestore ऑपरेटर को छोड़ने से बाद की सामग्री पर अवांछित परिवर्तन या सेटिंग लागू हो सकती हैं। इनका उपयोग करने से साफ ग्राफ़िक्स स्थिति बनाए रखने में मदद मिलती है।

#### प्रश्न: क्या मैं PDF दस्तावेज़ के विभिन्न पृष्ठों पर XForms का पुनः उपयोग कर सकता हूँ?

 उत्तर: हां, आप एक ही XForm को एकाधिक पृष्ठों पर जोड़कर XForms का पुनः उपयोग कर सकते हैं।`Resources.Forms` विभिन्न पृष्ठों का संग्रह.

#### प्रश्न: क्या मेरे द्वारा बनाए जा सकने वाले XForms की संख्या की कोई सीमा है?

उत्तर: हालाँकि, आपके द्वारा बनाए जा सकने वाले XForms की संख्या पर कोई सख्त सीमा नहीं है, लेकिन ध्यान रखें कि बहुत ज़्यादा XForms बनाने से प्रदर्शन और मेमोरी उपयोग पर असर पड़ सकता है। इनका विवेकपूर्ण तरीके से उपयोग करें।

#### प्रश्न: क्या मैं XForm को घुमा सकता हूँ या अन्य परिवर्तन लागू कर सकता हूँ?

 उत्तर: हां, आप इसका उपयोग कर सकते हैं`ConcatenateMatrix` ऑपरेटर का उपयोग XForm में रोटेशन, स्केलिंग और ट्रांसलेशन जैसे रूपांतरणों को लागू करने के लिए किया जाता है।
