---
title: पीडीएफ से एसवीजी
linktitle: पीडीएफ से एसवीजी
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF को SVG में बदलने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 180
url: /hi/net/document-conversion/pdf-to-svg/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ को एसवीजी प्रारूप में परिवर्तित करने की प्रक्रिया के बारे में बताएंगे। एसवीजी (स्केलेबल वेक्टर ग्राफिक्स) एक वेक्टर छवि प्रारूप है जो ग्राफिक्स की गुणवत्ता और स्केलिंग को बनाए रखने में मदद करता है। नीचे दिए गए चरणों का पालन करके, आप एक पीडीएफ फाइल को एसवीजी प्रारूप में परिवर्तित करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आप निम्नलिखित शर्तें पूरी करते हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है।
- विजुअल स्टूडियो जैसा विकास वातावरण।

## चरण 1: पीडीएफ दस्तावेज़ लोड हो रहा है
इस चरण में हम .NET के लिए Aspose.PDF का उपयोग करके स्रोत पीडीएफ फ़ाइल लोड करेंगे। नीचे दिए गए कोड का पालन करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// पीडीएफ दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "input.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` उस वास्तविक निर्देशिका के साथ जहां आपकी पीडीएफ फाइल स्थित है।

## चरण 2: एसवीजी सेव विकल्पों का इंस्टेंटेशन
पीडीएफ फाइल लोड करने के बाद, हम एसवीजी सेव विकल्पों को तुरंत सक्रिय करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// एक SvgSaveOptions ऑब्जेक्ट को इंस्टेंटियेट करें
SvgSaveOptions saveOptions = new SvgSaveOptions();
// ज़िप संग्रह में एसवीजी छवि को संपीड़ित न करें
saveOptions.CompressOutputToZipArchive = false;
```

## चरण 3: परिणामी एसवीजी फ़ाइल को सहेजना
अब हम परिवर्तित पीडीएफ फाइल को एसवीजी फॉर्मेट में सेव करने जा रहे हैं। निम्नलिखित कोड का प्रयोग करें:

```csharp
// आउटपुट को SVG फ़ाइलों में सहेजें
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 उपरोक्त कोड परिवर्तित पीडीएफ को फ़ाइल नाम के साथ एसवीजी प्रारूप में सहेजता है`"PDFToSVG_out.svg"`.

### .NET के लिए Aspose.PDF का उपयोग करके PDF से SVG के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// पीडीएफ दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "input.pdf");
// SvgSaveOptions के किसी ऑब्जेक्ट को इंस्टेंट करें
SvgSaveOptions saveOptions = new SvgSaveOptions();
// एसवीजी छवि को ज़िप संग्रह में संपीड़ित न करें
saveOptions.CompressOutputToZipArchive = false;
// आउटपुट को SVG फ़ाइलों में सहेजें
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फाइल को एसवीजी प्रारूप में परिवर्तित करने की चरण-दर-चरण प्रक्रिया को कवर किया। ऊपर बताए गए निर्देशों का पालन करके, अब आप एक पीडीएफ फाइल को एसवीजी प्रारूप में बदलने में सक्षम होंगे। यह सुविधा तब उपयोगी होती है जब आप वेक्टर छवियों में कनवर्ट करते समय ग्राफिक्स गुणवत्ता और स्केलिंग बनाए रखना चाहते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं पीडीएफ से एसवीजी रूपांतरण के दौरान परिणामी एसवीजी फाइलों के रिज़ॉल्यूशन या आकार को नियंत्रित कर सकता हूं?

 उ: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ से एसवीजी रूपांतरण के दौरान परिणामी एसवीजी फ़ाइलों के रिज़ॉल्यूशन या आकार को नियंत्रित कर सकते हैं।`SvgSaveOptions` वर्ग जैसे गुण प्रदान करता है`PageSavingCallback` और`SaveFormat` जो आपको एसवीजी आउटपुट से संबंधित रिज़ॉल्यूशन, पेज आकार या अन्य पैरामीटर सेट करने की अनुमति देता है। आप एसवीजी फ़ाइलों की गुणवत्ता और आकार को नियंत्रित करने के लिए इन विकल्पों को अपनी आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF एन्क्रिप्टेड या पासवर्ड-संरक्षित पीडीएफ को एसवीजी में परिवर्तित करने का समर्थन करता है?

उत्तर: हां, .NET के लिए Aspose.PDF एन्क्रिप्टेड या पासवर्ड-संरक्षित पीडीएफ को एसवीजी प्रारूप में परिवर्तित करने का समर्थन करता है। जब आप पासवर्ड-सुरक्षित पीडीएफ लोड करते हैं, तो आप इसका उपयोग करके पासवर्ड प्रदान कर सकते हैं`Document` क्लास कंस्ट्रक्टर या सेटिंग करके`Password` पीडीएफ लोड करने से पहले संपत्ति। .NET के लिए Aspose.PDF, PDF से SVG रूपांतरण प्रक्रिया के दौरान डिक्रिप्शन को संभालेगा।

#### प्रश्न: क्या मैं संपूर्ण दस्तावेज़ के बजाय पीडीएफ के केवल विशिष्ट पृष्ठों को एसवीजी में परिवर्तित कर सकता हूं?

उ: हाँ, आप .NET के लिए Aspose.PDF का उपयोग करके संपूर्ण दस्तावेज़ के बजाय PDF के केवल विशिष्ट पृष्ठों को SVG में परिवर्तित कर सकते हैं। आउटपुट को एसवीजी फ़ाइलों के रूप में सहेजने से पहले, आप उन पेजों का चयन कर सकते हैं जिन्हें आप उनके पेज नंबर या रेंज निर्दिष्ट करके कनवर्ट करना चाहते हैं। इस तरह, आप केवल वांछित पृष्ठों को पीडीएफ से एसवीजी प्रारूप में निकाल और परिवर्तित कर सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF SVG के सभी संस्करणों के साथ संगत है?

उत्तर: .NET के लिए Aspose.PDF को SVG 1.1 (स्केलेबल वेक्टर ग्राफ़िक्स) विनिर्देश के साथ संगत होने के लिए डिज़ाइन किया गया है। यह एसवीजी 1.1 मानक के अनुसार एसवीजी फ़ाइलें उत्पन्न करने का समर्थन करता है। हालाँकि, कृपया ध्यान दें कि SVG 2.0 को SVG विनिर्देश के नवीनतम संस्करण के रूप में पेश किया गया है। जबकि .NET के लिए Aspose.PDF अभी भी कई मामलों में SVG 2.0 के साथ अच्छा काम कर सकता है, यह अनुशंसा की जाती है कि आप जिन विशिष्ट SVG सुविधाओं का उपयोग करना चाहते हैं, उनके साथ संगतता और संभावित सीमाओं की जांच करें।