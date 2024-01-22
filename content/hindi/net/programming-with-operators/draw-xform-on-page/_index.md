---
title: पेज पर एक्सफॉर्म बनाएं
linktitle: पेज पर एक्सफॉर्म बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ पेज पर XForm फॉर्म बनाने के लिए चरण-दर-चरण मार्गदर्शिका। फ़ॉर्म जोड़ें और पृष्ठ पर रखें.
type: docs
weight: 10
url: /hi/net/programming-with-operators/draw-xform-on-page/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके किसी पेज पर XForm कैसे बनाएं, इसके बारे में चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको पीडीएफ दस्तावेजों को प्रोग्रामेटिक रूप से बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। Aspose.PDF द्वारा प्रदान किए गए ऑपरेटरों का उपयोग करके, आप मौजूदा पीडीएफ पेज पर एक एक्सफॉर्म फॉर्म जोड़ और रख सकते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. विजुअल स्टूडियो .NET फ्रेमवर्क के साथ स्थापित किया गया है।
2. .NET के लिए Aspose.PDF लाइब्रेरी।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, विज़ुअल स्टूडियो में एक नया प्रोजेक्ट बनाएं और .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें। आप Aspose की आधिकारिक वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं और इसे अपनी मशीन पर इंस्टॉल कर सकते हैं।

## चरण 2: आवश्यक नामस्थान आयात करें

अपनी C# कोड फ़ाइल में, Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## चरण 3: फ़ाइल पथ सेट करना

पृष्ठभूमि छवि, इनपुट पीडीएफ फ़ाइल और आउटपुट पीडीएफ फ़ाइल के लिए फ़ाइल पथ परिभाषित करें:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

अपनी मशीन पर वास्तविक फ़ाइल पथ निर्दिष्ट करना सुनिश्चित करें।

## चरण 4: इनपुट पीडीएफ फाइल लोड हो रही है

इनपुट पीडीएफ फाइल लोड करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// निम्नलिखित कोड GSave/GRestore ऑपरेटरों का उपयोग करता है
// कोड XForm को स्थान देने के लिए ContatenetMatrix ऑपरेटर का उपयोग करता है
// कोड पृष्ठ पर XForm बनाने के लिए Do ऑपरेटर का उपयोग करता है
// GSave/GRestore संचालक मौजूदा सामग्री को रैप करते हैं
// यह मौजूदा सामग्री के अंत में प्रारंभिक ग्राफ़िक्स स्थिति प्राप्त करने के लिए किया जाता है
// अन्यथा मौजूदा ऑपरेटरों की श्रृंखला के अंत में अवांछित परिवर्तन बचे रह सकते हैं
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// नए आदेशों के बाद ग्राफ़िक्स स्थिति को ठीक से रीसेट करने के लिए GSave ऑपरेटर जोड़ें
pageContents. Add(new GSave());

// एक्सफॉर्म बनाएं
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// छवि की चौड़ाई और ऊंचाई निर्धारित करें
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// छवि को एक स्ट्रीम में लोड करें
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// छवि को XForm संसाधन छवि संग्रह में जोड़ें
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Do ऑपरेटर का उपयोग करना: यह ऑपरेटर छवि खींचता है
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//XForm को निर्देशांक x=100 और y=500 पर रखें
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

// GSave के बाद GRestore के साथ ग्राफ़िक्स स्थिति पुनर्स्थापित करें
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

वास्तविक फ़ाइल पथ निर्दिष्ट करना सुनिश्चित करें और आवश्यकतानुसार पृष्ठ संख्या और XForm स्थिति समायोजित करें।

### .NET के लिए Aspose.PDF का उपयोग करके पृष्ठ पर XForm बनाने के लिए नमूना स्रोत कोड
 
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
	// GSave/GRestore ऑपरेटरों का उपयोग
	// xForm को स्थान देने के लिए ContatenetMatrix ऑपरेटर का उपयोग
	// पृष्ठ पर xForm बनाने के लिए ऑपरेटर का उपयोग करें
	// मौजूदा सामग्री को GSave/GRestore ऑपरेटर जोड़ी के साथ लपेटें
	// इसका उद्देश्य मौजूदा सामग्रियों की आरंभिक ग्राफ़िक्स स्थिति प्राप्त करना है
	// अन्यथा मौजूदा ऑपरेटर श्रृंखला के अंत में कुछ अवांछनीय परिवर्तन रह सकते हैं
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// नए आदेशों के बाद ग्राफ़िक्स स्थिति को ठीक से साफ़ करने के लिए सेव ग्राफ़िक्स स्टेट ऑपरेटर जोड़ें
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// एक्सफॉर्म बनाएं
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// छवि की चौड़ाई और ऊँचाई को परिभाषित करें
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// छवि को स्ट्रीम में लोड करें
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//XForm संसाधनों के छवि संग्रह में छवि जोड़ें
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Do ऑपरेटर का उपयोग करना: यह ऑपरेटर छवि बनाता है
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// फॉर्म को x=100 y=500 निर्देशांक पर रखें
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// डू ऑपरेटर के साथ फॉर्म बनाएं
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// x=100 y=300 निर्देशांकों पर प्रपत्र रखें
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// डू ऑपरेटर के साथ फॉर्म बनाएं
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// GSave के बाद GRestore के साथ ग्राफिक्स स्थिति को पुनर्स्थापित करें
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ पेज पर XForm फॉर्म कैसे बनाया जाता है। वर्णित चरणों का पालन करके, आप मौजूदा पृष्ठ पर एक एक्सफॉर्म फॉर्म जोड़ने और रखने में सक्षम होंगे, इस प्रकार आपके पीडीएफ दस्तावेज़ों को अधिक लचीलापन मिलेगा।

### पृष्ठ पर XForm निकालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: Aspose.PDF में XForm क्या है?

उ: एक XForm एक पीडीएफ दस्तावेज़ में एक पुन: प्रयोज्य ग्राफ़िकल ऑब्जेक्ट है। यह आपको जटिल ग्राफिक्स, छवियों या टेक्स्ट को परिभाषित करने और चित्रित करने की अनुमति देता है जिन्हें विभिन्न पृष्ठों पर कई बार पुन: उपयोग किया जा सकता है।

#### प्रश्न: मैं Aspose.PDF के लिए आवश्यक नामस्थान कैसे आयात करूं?

 उ: अपनी C# कोड फ़ाइल में, का उपयोग करें`using` Aspose.PDF द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थान आयात करने का निर्देश:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### प्रश्न: GSave और GRestore ऑपरेटरों का उद्देश्य क्या है?

 ए: द`GSave` और`GRestore`Aspose.PDF में ऑपरेटरों का उपयोग ग्राफ़िक्स स्थिति को सहेजने और पुनर्स्थापित करने के लिए किया जाता है। वे यह सुनिश्चित करने में मदद करते हैं कि सामग्री के एक अनुभाग पर लागू किए गए परिवर्तन और सेटिंग्स अगले अनुभागों को प्रभावित नहीं करते हैं।

#### प्रश्न: मैं Aspose.PDF का उपयोग करके XForm को कैसे परिभाषित करूं?

 उत्तर: XForm बनाने के लिए, इसका उपयोग करें`XForm.CreateNewForm` विधि और इसे इसमें जोड़ें`Resources.Forms` किसी विशिष्ट पृष्ठ का संग्रह. फिर आप XForm में सामग्री जोड़ सकते हैं`Contents` संपत्ति।

#### प्रश्न: मैं एक्सफॉर्म के भीतर एक छवि कैसे बना सकता हूं?

 उ: छवि को एक स्ट्रीम में लोड करें और इसे इसमें जोड़ें`Resources.Images` एक्सफॉर्म का संग्रह। उपयोग`Do` XForm के भीतर ऑपरेटर`Contents` छवि बनाने के लिए.

#### प्रश्न: मैं पीडीएफ पेज पर एक्सफॉर्म कैसे रखूं?

 उ: किसी पृष्ठ पर XForm को स्थापित करने के लिए, इसका उपयोग करें`ConcatenateMatrix` पेज के भीतर ऑपरेटर`Contents`. XForm के अनुवाद (स्थिति) और स्केलिंग को निर्दिष्ट करने के लिए मैट्रिक्स पैरामीटर समायोजित करें।

#### प्रश्न: क्या मैं एक ही पृष्ठ पर अनेक XForms बना सकता हूँ?

 उत्तर: हाँ, आप इसे समायोजित करके एक ही पृष्ठ पर एकाधिक XForms बना सकते हैं`ConcatenateMatrix`प्रत्येक XForm को अलग-अलग निर्देशांक पर स्थित करने के लिए पैरामीटर।

#### प्रश्न: क्या मैं XForm बनने के बाद उसकी सामग्री को संशोधित कर सकता हूँ?

 उत्तर: हाँ, आप निर्माण के बाद XForm में अतिरिक्त ऑपरेटर जोड़कर इसकी सामग्री को संशोधित कर सकते हैं`Contents` संपत्ति।

#### प्रश्न: यदि मैं GSave और GRestore ऑपरेटरों को छोड़ दूं तो क्या होगा?

उ: GSave और GRestore ऑपरेटरों को छोड़ने से बाद की सामग्री पर अवांछित परिवर्तन या सेटिंग्स लागू हो सकती हैं। उनका उपयोग करने से साफ़ ग्राफ़िक्स स्थिति बनाए रखने में मदद मिलती है।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ के विभिन्न पृष्ठों पर एक्सफॉर्म का पुन: उपयोग कर सकता हूं?

 उत्तर: हाँ, आप एक ही XForm को इसमें जोड़कर कई पृष्ठों पर XForms का पुन: उपयोग कर सकते हैं`Resources.Forms` विभिन्न पृष्ठों का संग्रह.

#### प्रश्न: क्या मेरे द्वारा बनाए जा सकने वाले XForms की संख्या की कोई सीमा है?

उ: हालाँकि आपके द्वारा बनाए जा सकने वाले XForms की संख्या की कोई सख्त सीमा नहीं है, ध्यान रखें कि बहुत सारे XForms प्रदर्शन और मेमोरी उपयोग को प्रभावित कर सकते हैं। इनका उपयोग सोच-समझकर करें।

#### प्रश्न: क्या मैं XForm को घुमा सकता हूँ या अन्य परिवर्तन लागू कर सकता हूँ?

 उत्तर: हाँ, आप इसका उपयोग कर सकते हैं`ConcatenateMatrix`ऑपरेटर को XForm में रोटेशन, स्केलिंग और अनुवाद जैसे परिवर्तन लागू करने होंगे।
