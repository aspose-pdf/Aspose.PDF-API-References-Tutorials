---
title: पीडीएफ फाइल में छिपा हुआ टेक्स्ट जोड़ें और खोजें
linktitle: पीडीएफ फाइल में छिपा हुआ टेक्स्ट जोड़ें और खोजें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छिपे हुए पाठ को जोड़ने और खोजने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 20
url: /hi/net/programming-with-text/add-and-search-hidden-text/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छिपे हुए टेक्स्ट को जोड़ने और खोजने का तरीका बताएँगे। इस ऑपरेशन को आसानी से करने के लिए इन चरणों का पालन करें।

## 1. पूर्वापेक्षाएँ

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो या कोई अन्य विकास वातावरण स्थापित और कॉन्फ़िगर किया गया।
- C# प्रोग्रामिंग भाषा का मूलभूत ज्ञान।
- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है। आप इसे Aspose की आधिकारिक वेबसाइट से डाउनलोड कर सकते हैं।

## 2. छिपे हुए पाठ के साथ पीडीएफ दस्तावेज़ बनाना

आरंभ करने के लिए, छिपे हुए पाठ वाले एक नए पीडीएफ दस्तावेज़ बनाने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// दस्तावेज़ बनाएँ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// टेक्स्ट गुण सेट करें - अदृश्य
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

पीडीएफ दस्तावेज़ के लिए वांछित पथ और फ़ाइल नाम प्रदान करना सुनिश्चित करें।

## 3. दस्तावेज़ में पाठ खोजें

अब हम PDF दस्तावेज़ में छिपे हुए टेक्स्ट को खोजेंगे। इसके लिए निम्न कोड का उपयोग करें:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//टुकड़ों के साथ कुछ करो
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

यह पीडीएफ दस्तावेज़ के दूसरे पृष्ठ में छिपे हुए पाठ को खोजेगा और प्रासंगिक जानकारी प्रदर्शित करेगा।

### .NET के लिए Aspose.PDF का उपयोग करके छिपे हुए टेक्स्ट को जोड़ने और खोजने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//छिपे हुए पाठ के साथ दस्तावेज़ बनाएँ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//टेक्स्ट गुण सेट करें - अदृश्य
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//दस्तावेज़ में पाठ खोजें
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//टुकड़ों के साथ कुछ करें
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में छिपे हुए पाठ को सफलतापूर्वक जोड़ा और पाया है। अब आप PDF फ़ाइलों में छिपे हुए पाठ को बदलने और खोजने के लिए इस विधि को अपने स्वयं के प्रोजेक्ट पर लागू कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उत्तर: .NET के लिए Aspose.PDF एक मजबूत लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों के भीतर PDF दस्तावेज़ बनाने, हेरफेर करने और बदलने की शक्ति प्रदान करती है।

#### प्रश्न: क्या छिपे हुए पाठ का उपयोग वॉटरमार्किंग के लिए किया जा सकता है?

उत्तर: बिल्कुल! छिपा हुआ पाठ पीडीएफ दस्तावेजों पर वॉटरमार्क लगाने के प्रभावी साधन के रूप में काम कर सकता है, जिससे सुरक्षा की एक अतिरिक्त परत जुड़ जाती है।

#### प्रश्न: क्या पीडीएफ दस्तावेज़ में छिपे पाठ को प्रकट करना संभव है?

उत्तर: हां, पीडीएफ दस्तावेज़ में छिपे हुए पाठ को खोजने और प्रकट करने की प्रक्रिया इस ट्यूटोरियल में बताई गई तकनीकों का उपयोग करके प्राप्त की जा सकती है।

#### प्रश्न: .NET के लिए Aspose.PDF अन्य कौन सी कार्यक्षमताएं प्रदान करता है?

उत्तर: छिपे हुए पाठ हेरफेर के अलावा, .NET के लिए Aspose.PDF कई प्रकार की सुविधाएँ प्रदान करता है, जिसमें PDF निर्माण, रूपांतरण, एन्क्रिप्शन और बहुत कुछ शामिल है।