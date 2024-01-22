---
title: मल्टीलेयर पीडीएफ फाइल दूसरा दृष्टिकोण बनाएं
linktitle: मल्टीलेयर पीडीएफ फाइल दूसरा दृष्टिकोण बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके मल्टीलेयर PDF फ़ाइल बनाना सीखें। पाठ और छवियों के साथ गतिशील पीडीएफ़ बनाने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 80
url: /hi/net/programming-with-document/createmultilayerpdfsecondapproach/
---
इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.PDF में दूसरे दृष्टिकोण का उपयोग करके एक मल्टीलेयर पीडीएफ फाइल कैसे बनाई जाए। हम विस्तृत स्पष्टीकरण के साथ चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे और पूर्ण स्रोत कोड शामिल करेंगे। इस ट्यूटोरियल का अनुसरण करके, आप अपने .NET अनुप्रयोगों में Aspose.PDF लाइब्रेरी का उपयोग करके कई परतों के साथ पीडीएफ दस्तावेज़ तैयार करने में सक्षम होंगे।

अब, आइए चरण-दर-चरण मार्गदर्शिका के साथ शुरुआत करें।

## चरण 1: पर्यावरण स्थापित करें

आरंभ करने के लिए, विज़ुअल स्टूडियो खोलें और एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में Aspose.PDF लाइब्रेरी का संदर्भ लिया है। एक बार जब आप वातावरण स्थापित कर लेते हैं, तो आप अगले चरण पर आगे बढ़ने के लिए तैयार होते हैं।

## चरण 2: वेरिएबल प्रारंभ करें

इस चरण में, हम आवश्यक वेरिएबल प्रारंभ करेंगे। हमें दस्तावेज़ निर्देशिका के लिए पथ सेट करने और पीडीएफ परतों के लिए रंग चर परिभाषित करने की आवश्यकता है। यहाँ कोड स्निपेट है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## चरण 3: एक पीडीएफ दस्तावेज़ बनाएं

इसके बाद, हम Aspose.Pdf.Document वर्ग का एक नया उदाहरण बनाएंगे, जो एक पीडीएफ दस्तावेज़ का प्रतिनिधित्व करता है। यहाँ कोड स्निपेट है:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## चरण 4: दस्तावेज़ में एक पेज जोड़ें

इस चरण में, हम पीडीएफ दस्तावेज़ में एक नया पेज जोड़ेंगे। यहाँ कोड स्निपेट है:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## चरण 5: पृष्ठ पर टेक्स्ट जोड़ें

अब, हम पृष्ठ पर एक पाठ खंड जोड़ेंगे। पाठ को लाल रंग के साथ पैराग्राफ 3 खंड के रूप में प्रदर्शित किया जाएगा। यहाँ कोड स्निपेट है:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## चरण 6: पृष्ठ पर एक छवि जोड़ें

इस चरण में, हम पृष्ठ पर एक छवि जोड़ेंगे। छवि को एक विशिष्ट आकार के साथ एक फ़्लोटिंग बॉक्स के रूप में स्थित किया जाएगा। यहाँ कोड स्निपेट है:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## चरण 7: पीडीएफ को सेव करें

इस चरण में, हम पीडीएफ को एक फ़ाइल में सहेजेंगे।

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके मल्टीलेयर पीडीएफ द्वितीय दृष्टिकोण बनाने के लिए उदाहरण स्रोत कोड।

```csharp   
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## निष्कर्ष

इस लेख में, हमने सीखा है कि .NET के लिए Aspose.PDF के दूसरे दृष्टिकोण का उपयोग करके एक मल्टीलेयर पीडीएफ कैसे बनाया जाए। हमने आपको चरण-दर-चरण निर्देश और मल्टीलेयर पीडीएफ बनाने के लिए आवश्यक पूर्ण स्रोत कोड प्रदान किया है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके मल्टीलेयर पीडीएफ बनाने का दूसरा तरीका क्या है?

उ: .NET के लिए Aspose.PDF का उपयोग करके मल्टीलेयर पीडीएफ बनाने के दूसरे दृष्टिकोण में पीडीएफ दस्तावेज़ के भीतर विभिन्न परतों में सामग्री तत्वों, जैसे पाठ और छवियों को जोड़ने और जोड़ने के लिए फ्लोटिंग बॉक्स का उपयोग करना शामिल है।

#### प्रश्न: क्या मैं दूसरे दृष्टिकोण का उपयोग करके पीडीएफ दस्तावेज़ में दो से अधिक परतें जोड़ सकता हूं?

उ: हाँ, आप दूसरे दृष्टिकोण का उपयोग करके अधिक फ़्लोटिंग बॉक्स जोड़कर और उन्हें तदनुसार स्थिति देकर पीडीएफ दस्तावेज़ में कई परतें जोड़ सकते हैं। प्रत्येक फ़्लोटिंग बॉक्स एक अलग परत का प्रतिनिधित्व करता है, और आप कई परतें बनाने के लिए प्रत्येक बॉक्स में सामग्री तत्व जोड़ सकते हैं।

#### प्रश्न: मल्टीलेयर पीडीएफ़ बनाने के लिए दूसरे दृष्टिकोण का उपयोग करने के क्या लाभ हैं?

उ: दूसरा दृष्टिकोण पीडीएफ दस्तावेज़ में सामग्री तत्वों की स्थिति और दृश्यता पर सटीक नियंत्रण की अनुमति देता है। यह परतों और सामग्री व्यवस्था को प्रबंधित करने में अधिक लचीलापन प्रदान करता है, जिससे जटिल और इंटरैक्टिव दस्तावेज़ बनाना आसान हो जाता है।

#### प्रश्न: क्या .NET के लिए Aspose.PDF जटिल और इंटरैक्टिव पीडीएफ दस्तावेज़ बनाने के लिए उपयुक्त है?

उत्तर: हाँ, .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो जटिल और इंटरैक्टिव पीडीएफ दस्तावेज़ बनाने के लिए व्यापक सुविधाएँ प्रदान करती है। यह कार्यात्मकताओं की एक विस्तृत श्रृंखला प्रदान करता है, जैसे पाठ, चित्र, तालिकाएँ, हाइपरलिंक और फॉर्म फ़ील्ड जोड़ना, साथ ही उन्नत पीडीएफ संचालन का समर्थन करना।

#### प्रश्न: क्या मैं दूसरे दृष्टिकोण में फ़्लोटिंग बॉक्स की उपस्थिति और गुणों को अनुकूलित कर सकता हूँ?

उ: हाँ, आप फ़्लोटिंग बॉक्स की उपस्थिति और गुणों को अनुकूलित कर सकते हैं, जैसे कि उनका आकार, स्थिति, पृष्ठभूमि का रंग और अस्पष्टता। .NET के लिए Aspose.PDF फ़्लोटिंग बॉक्स की स्टाइलिंग और स्थिति के लिए विभिन्न विकल्प प्रदान करता है।