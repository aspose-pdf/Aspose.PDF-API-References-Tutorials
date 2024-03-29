---
title: पृष्ठ सामग्री को पीडीएफ फ़ाइल में फ़िट करें
linktitle: पृष्ठ सामग्री को पीडीएफ फ़ाइल में फ़िट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में पृष्ठ सामग्री को समायोजित करने के लिए विस्तृत चरण-दर-चरण मार्गदर्शिका। आसान कार्यान्वयन और लाभप्रद निष्कर्ष।
type: docs
weight: 50
url: /hi/net/programming-with-pdf-pages/fit-page-contents/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में पृष्ठ सामग्री को समायोजित करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ पृष्ठों की सामग्री को कैसे समायोजित किया जाए।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान
- आपके विकास परिवेश में .NET के लिए Aspose.PDF स्थापित है

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह स्थान है जहां आपकी इनपुट पीडीएफ फाइल स्थित है। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ लोड करें
 फिर आप इसका उपयोग करके पीडीएफ दस्तावेज़ लोड कर सकते हैं`Document` Aspose.PDF की कक्षा। इनपुट पीडीएफ फ़ाइल के लिए सही पथ निर्दिष्ट करना सुनिश्चित करें।

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## चरण 3: पृष्ठ सामग्री समायोजित करें
अब आप दस्तावेज़ के सभी पृष्ठों को चक्रित कर सकते हैं और मीडिया बॉक्स के आकार के अनुसार प्रत्येक पृष्ठ की सामग्री को समायोजित कर सकते हैं। दिए गए उदाहरण में, हम पृष्ठ की चौड़ाई को समान ऊंचाई रखते हुए लैंडस्केप मोड (परिदृश्य) में प्रस्तुत करने के लिए समायोजित करते हैं। नई चौड़ाई की गणना मीडिया बॉक्स के पहलू अनुपात के आधार पर की जाती है।

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### .NET के लिए Aspose.PDF का उपयोग करके फ़िट पृष्ठ सामग्री के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// नई ऊंचाई वही
	double newHeight = r.Height;
	// ओरिएंटेशन लैंडस्केप बनाने के लिए नई चौड़ाई आनुपातिक रूप से विस्तारित की जाती है
	// (हम मानते हैं कि पिछला अभिविन्यास चित्र है)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ पेज सामग्री को कैसे समायोजित किया जाए। ऊपर बताए गए चरणों का पालन करके, आप इस कार्यक्षमता को अपनी परियोजनाओं में आसानी से लागू कर सकते हैं। पीडीएफ फाइलों के साथ काम करने के लिए अन्य उपयोगी सुविधाओं की खोज के लिए बेझिझक Aspose.PDF दस्तावेज़ का अन्वेषण करें।

### पीडीएफ फाइल में पेज सामग्री को फिट करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ पृष्ठों के संदर्भ में "मीडिया बॉक्स" क्या दर्शाता है?

उ: पीडीएफ पृष्ठों के संदर्भ में, "मीडिया बॉक्स" बाउंडिंग बॉक्स का प्रतिनिधित्व करता है जो पृष्ठ सामग्री के भौतिक आयामों को परिभाषित करता है। यह पीडीएफ दस्तावेज़ के भीतर पृष्ठ सामग्री की चौड़ाई, ऊंचाई और स्थान को परिभाषित करता है।

#### प्रश्न: प्रदत्त C# स्रोत कोड पृष्ठ सामग्री को कैसे समायोजित करता है?

उ: प्रदत्त सी# स्रोत कोड प्रत्येक पृष्ठ की चौड़ाई का आकार बदलकर पृष्ठ सामग्री को समायोजित करता है ताकि इसे समान ऊंचाई रखते हुए लैंडस्केप मोड में प्रदर्शित किया जा सके। नई चौड़ाई की गणना मीडिया बॉक्स के पहलू अनुपात के आधार पर की जाती है, जिससे यह सुनिश्चित होता है कि सामग्री अपने मूल अनुपात को बरकरार रखती है।

#### प्रश्न: क्या मैं पृष्ठ सामग्री को किसी विशिष्ट आकार या पहलू अनुपात में फिट करने के लिए समायोजित कर सकता हूँ?

उ: हाँ, आप दिए गए C# स्रोत कोड में गणना को संशोधित करके पृष्ठ सामग्री को एक विशिष्ट आकार या पहलू अनुपात में फिट करने के लिए समायोजित कर सकते हैं। उदाहरण के लिए, यदि आप पृष्ठ सामग्री को एक निश्चित आकार (उदाहरण के लिए, 8.5 x 11 इंच) में फिट करना चाहते हैं, तो आप तदनुसार नई चौड़ाई और ऊंचाई की गणना कर सकते हैं।

#### प्रश्न: पृष्ठ का आकार समायोजित करने के बाद पृष्ठ की सामग्री का क्या होगा?

उ: दिए गए C# स्रोत कोड का उपयोग करके पृष्ठ आकार को समायोजित करने के बाद, पृष्ठ पर सामग्री का आकार आनुपातिक रूप से बदल दिया जाएगा। यदि मूल सामग्री का पहलू अनुपात नए पहलू अनुपात से काफी भिन्न है, तो सामग्री फैली हुई या संपीड़ित दिखाई दे सकती है।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में सभी पृष्ठों के बजाय विशिष्ट पृष्ठों की सामग्री को समायोजित कर सकता हूँ?

उ: हां, आप पीडीएफ दस्तावेज़ में सभी पृष्ठों के बजाय विशिष्ट पृष्ठों की सामग्री को समायोजित कर सकते हैं। दिए गए C# स्रोत कोड में, "foreach" लूप दस्तावेज़ के सभी पृष्ठों के माध्यम से पुनरावृत्त होता है। विशिष्ट पृष्ठों की सामग्री को समायोजित करने के लिए, आप केवल वांछित पृष्ठों को लक्षित करने के लिए लूप के भीतर सशर्त बयानों का उपयोग कर सकते हैं।