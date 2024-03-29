---
title: पीडीएफ फाइल से छवियाँ निकालें
linktitle: पीडीएफ फाइल से छवियाँ निकालें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ आसानी से PDF फ़ाइल से छवियां निकालें।
type: docs
weight: 120
url: /hi/net/programming-with-images/extract-images/
---
यह मार्गदर्शिका आपको चरण दर चरण बताएगी कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल से छवियां कैसे निकालें। सुनिश्चित करें कि आपने अपना परिवेश पहले ही सेट कर लिया है और नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें

 शुरू करने से पहले, सुनिश्चित करें कि आपने दस्तावेज़ों के लिए सही निर्देशिका सेट की है। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` कोड में उस निर्देशिका के पथ के साथ जहां आपका पीडीएफ दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ खोलें

इस चरण में, हम इसका उपयोग करके पीडीएफ दस्तावेज़ खोलेंगे`Document` Aspose.PDF की कक्षा। उपयोग`Document` कंस्ट्रक्टर और पीडीएफ दस्तावेज़ के लिए पथ पास करें।

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## चरण 3: एक विशिष्ट छवि निकालें

 इस चरण में, हम एक विशेष पृष्ठ से एक विशिष्ट छवि निकालने जा रहे हैं। उपयोग`Images` पेज का संग्रह`s `वांछित छवि तक पहुंचने के लिए संसाधन ऑब्जेक्ट। नीचे दिए गए उदाहरण में, हम पहले पृष्ठ से इंडेक्स 1 के साथ छवि निकालते हैं।

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## चरण 4: निकाली गई छवि को सहेजें

 का उपयोग करके निकाली गई छवि को फ़ाइल में सहेजें`Save` की विधि`xImage` वस्तु। आउटपुट पथ और छवि प्रारूप निर्दिष्ट करें (इस उदाहरण में हम JPEG प्रारूप का उपयोग कर रहे हैं)।

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## चरण 5: अद्यतन पीडीएफ फाइल को सहेजें

 का उपयोग करके अपडेट की गई पीडीएफ फाइल को सेव करें`Save` की विधि`pdfDocument` वस्तु। पीडीएफ फ़ाइल के लिए आउटपुट पथ निर्दिष्ट करें।

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके छवियाँ निकालने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// एक विशेष छवि निकालें
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// आउटपुट छवि सहेजें
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// अपडेट की गई पीडीएफ फाइल को सेव करें
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF से सफलतापूर्वक छवियां निकाली हैं। निकाली गई छवि निर्दिष्ट निर्देशिका में सहेजी जाती है और अद्यतन पीडीएफ फ़ाइल भी सहेजी जाती है। अब आप इन फ़ाइलों का उपयोग अपनी विशिष्ट आवश्यकताओं के लिए कर सकते हैं।

### पीडीएफ फ़ाइल से छवियाँ निकालने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल से छवियां क्यों निकालना चाहूंगा?

उ: पीडीएफ फाइल से छवियां निकालना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है जैसे संग्रह करना, अन्य दस्तावेजों में छवियों का पुन: उपयोग करना, सामग्री का विश्लेषण करना, या छवि प्रसंस्करण कार्य करना।

#### प्रश्न: .NET के लिए Aspose.PDF एक PDF दस्तावेज़ से छवियों को निकालने की सुविधा कैसे प्रदान करता है?

उ: .NET के लिए Aspose.PDF एक पीडीएफ दस्तावेज़ खोलने, विशिष्ट छवियों तक पहुंचने और विभिन्न प्रारूपों का उपयोग करके उन्हें छवि फ़ाइलों में सहेजने के लिए चरण-दर-चरण प्रक्रिया प्रदान करता है।

####  प्रश्न: क्या भूमिका है`Document` class in Aspose.PDF for .NET play in image extraction?

 ए: द`Document` क्लास का उपयोग पीडीएफ दस्तावेजों को लोड करने और हेरफेर करने के लिए किया जाता है। इस संदर्भ में, यह पीडीएफ दस्तावेज़ को खोलने में मदद करता है जिससे छवियां निकाली जाएंगी।

#### प्रश्न: मैं उस विशिष्ट छवि को कैसे निर्दिष्ट करूं जिसे मैं पीडीएफ पेज से निकालना चाहता हूं?

उत्तर: आप इसका उपयोग कर सकते हैं`Images` पेज का संग्रह`Resources` अपने सूचकांक द्वारा वांछित छवि तक पहुँचने के लिए ऑब्जेक्ट। उदाहरण के लिए,`pdfDocument.Pages[1].Resources.Images[1]` पहले पृष्ठ पर पहली छवि तक पहुँचता है।

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ के किसी भी पृष्ठ से छवियां निकाल सकता हूं?

उत्तर: हां, आप वांछित पेज इंडेक्स और निकाली जाने वाली छवि के इंडेक्स को निर्दिष्ट करके पीडीएफ दस्तावेज़ में किसी भी पेज से छवियां निकाल सकते हैं।

#### प्रश्न: मैं निकाली गई छवियों को किस छवि प्रारूप में सहेज सकता हूं?

 उ: आप निकाली गई छवियों को इसके द्वारा समर्थित विभिन्न प्रारूपों में सहेज सकते हैं`ImageFormat` एनम, जैसे जेपीईजी, पीएनजी, बीएमपी, और बहुत कुछ।

#### प्रश्न: मैं निकाली गई छवियों को फ़ाइलों में सहेजने के बाद उनका उपयोग कैसे कर सकता हूं?

उ: निकाली गई छवियों का उपयोग किसी अन्य छवि फ़ाइलों की तरह किया जा सकता है। आप उन्हें देख सकते हैं, संपादित कर सकते हैं, साझा कर सकते हैं या उन्हें अन्य दस्तावेज़ों या परियोजनाओं में शामिल कर सकते हैं।

#### प्रश्न: क्या पीडीएफ से छवियां निकालने से मूल पीडीएफ दस्तावेज़ का लेआउट या सामग्री प्रभावित होती है?

उ: नहीं, पीडीएफ से छवियां निकालने से मूल पीडीएफ दस्तावेज़ के लेआउट या सामग्री पर कोई असर नहीं पड़ता है। केवल निकाली गई छवियां ही प्रभावित होती हैं.

#### प्रश्न: क्या मैं एक ही प्रक्रिया में विभिन्न पृष्ठों से अनेक छवियाँ निकाल सकता हूँ?

उत्तर: हां, आप अलग-अलग पृष्ठ सूचकांकों के माध्यम से पुनरावृत्ति करके एकाधिक पृष्ठों से छवियां निकालने के लिए एक ही प्रक्रिया का उपयोग कर सकते हैं।