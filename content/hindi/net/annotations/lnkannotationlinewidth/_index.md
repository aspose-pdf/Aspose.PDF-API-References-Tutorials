---
title: एलएनके एनोटेशन लाइन चौड़ाई
linktitle: एलएनके एनोटेशन लाइन चौड़ाई
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: यह आलेख .NET के लिए Aspose.PDF का उपयोग करके एलएनके एनोटेशन की लाइन चौड़ाई निर्धारित करने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करता है।
type: docs
weight: 110
url: /hi/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF .NET अनुप्रयोगों में PDF फ़ाइलों के साथ काम करने के लिए एक शक्तिशाली और व्यापक रूप से उपयोग किया जाने वाला उपकरण है। यह पीडीएफ फाइलों को बनाने, संपादित करने और हेरफेर करने के लिए विभिन्न प्रकार की सुविधाएँ प्रदान करता है, जिसमें पृष्ठों पर एनोटेशन जोड़ने की क्षमता भी शामिल है। इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF का उपयोग करके लिंक एनोटेशन की लाइन चौड़ाई कैसे सेट करें।

एक बार जब आपके पास ये पूर्वापेक्षाएँ हों, तो विज़ुअल स्टूडियो में एक नया कंसोल एप्लिकेशन प्रोजेक्ट बनाएं। फिर, सॉल्यूशन एक्सप्लोरर में प्रोजेक्ट पर राइट-क्लिक करके, "न्यूगेट पैकेज प्रबंधित करें" का चयन करके और नुगेट पैकेज मैनेजर में "एस्पोस.पीडीएफ" की खोज करके .NET लाइब्रेरी के लिए Aspose.PDF का संदर्भ जोड़ें।

किसी पीडीएफ दस्तावेज़ में एलएनके एनोटेशन जोड़ने के लिए, इन चरणों का पालन करें:

##  चरण 1: एक नया बनाएं`Document` object.
```csharp
Document doc = new Document();
```
## चरण 2: दस्तावेज़ में एक नया पृष्ठ जोड़ें।
```csharp
doc.Pages.Add();
```
##  चरण 3: की एक सूची बनाएं`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  चरण 4: एक नया बनाएं`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  चरण 5: एक नया बनाएं`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## चरण 6: इशारे को स्याही इशारों की सूची में जोड़ें।
```csharp
inkList.Add(gesture);
```
##  चरण 7: एक नया बनाएं`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## चरण 8: एनोटेशन का विषय और शीर्षक सेट करें।
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## चरण 9: एनोटेशन का रंग सेट करें।
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  चरण 10: एक नया बनाएं`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## चरण 11: पृष्ठ पर एनोटेशन जोड़ें।
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## चरण 12: दस्तावेज़ को एक फ़ाइल में सहेजें।
```csharp
// आउटपुट फ़ाइल सहेजें
doc.Save(dataDir);


```
### उदाहरण .NET के लिए Aspose.PDF के साथ एलएनके एनोटेशन लाइन चौड़ाई दिखाता है

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// आउटपुट फ़ाइल सहेजें
doc.Save(dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में लिंक एनोटेशन की लाइन चौड़ाई कैसे सेट करें। .NET के लिए Aspose.PDF, PDF दस्तावेज़ों के साथ काम करने के लिए टूल और सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें लिंक एनोटेशन बनाने और अनुकूलित करने की क्षमता भी शामिल है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# स्रोत कोड का उपयोग करके, डेवलपर्स आसानी से अपने पीडीएफ दस्तावेज़ों में इंटरैक्टिव लिंक जोड़ सकते हैं, जिससे उपयोगकर्ता अनुभव और उनके अनुप्रयोगों की इंटरएक्टिविटी बढ़ सकती है। .NET के लिए Aspose.PDF एक बहुमुखी लाइब्रेरी है जो .NET डेवलपर्स को पीडीएफ फाइलों के साथ कुशलतापूर्वक और प्रभावी ढंग से काम करने में सक्षम बनाती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में लिंक एनोटेशन क्या है?

उ: पीडीएफ दस्तावेज़ में एक लिंक एनोटेशन एक इंटरैक्टिव तत्व है जो आपको हाइपरलिंक या क्रियाएं बनाने की अनुमति देता है जो उपयोगकर्ता को उसी दस्तावेज़, एक बाहरी वेबसाइट या एक अलग पीडीएफ दस्तावेज़ के भीतर किसी अन्य स्थान पर निर्देशित करता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके लिंक एनोटेशन की लाइन चौड़ाई कैसे निर्धारित कर सकता हूं?

उ: .NET के लिए Aspose.PDF का उपयोग करके लिंक एनोटेशन की लाइन चौड़ाई सेट करने के लिए, आप एक बना सकते हैं`InkAnnotation` ऑब्जेक्ट बनाएं और लाइन चौड़ाई गुण निर्दिष्ट करें।

#### प्रश्न: .NET के लिए Aspose.PDF में लिंक एनोटेशन के लिए कौन से गुणों को अनुकूलित किया जा सकता है?

उ: आप .NET के लिए Aspose.PDF में एक लिंक एनोटेशन के विभिन्न गुणों को अनुकूलित कर सकते हैं, जैसे कि इसका स्थान, आकार, रंग, सीमा गुण (चौड़ाई, शैली, डैश पैटर्न और प्रभाव), विषय, शीर्षक और दृश्यता।

#### प्रश्न: क्या मैं एक लिंक एनोटेशन बना सकता हूं जिसमें एकाधिक स्याही संकेत शामिल हों?

 उ: हाँ, आप एक लिंक एनोटेशन बना सकते हैं जिसमें एकाधिक स्याही संकेत शामिल हैं`Point` सरणियों को`InkAnnotation` वस्तु।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ के किसी विशिष्ट पृष्ठ पर एक लिंक एनोटेशन कैसे जोड़ सकता हूं?

 उ: पीडीएफ दस्तावेज़ के किसी विशिष्ट पृष्ठ पर एक लिंक एनोटेशन जोड़ने के लिए, आपको बनाते समय पृष्ठ संख्या निर्दिष्ट करनी होगी`InkAnnotation` वस्तु। उदाहरण के लिए,`new InkAnnotation(doc.Pages[1], ...)` प्रथम पृष्ठ पर लिंक एनोटेशन जोड़ता है।