---
title: HTML से कनवर्ट करने के बाद हाइपरलिंक हटा दें
linktitle: HTML से कनवर्ट करने के बाद हाइपरलिंक हटा दें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके HTML को PDF में परिवर्तित करने के बाद हाइपरलिंक हटाने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 250
url: /hi/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके HTML फ़ाइल से उत्पन्न पीडीएफ फ़ाइल से हाइपरलिंक हटाने की प्रक्रिया के बारे में बताएंगे। हाइपरलिंक क्लिक करने योग्य लिंक होते हैं जो अन्य पेजों या वेबसाइटों पर रीडायरेक्ट हो सकते हैं। नीचे दिए गए चरणों का पालन करके, आप परिणामी पीडीएफ फ़ाइल से हाइपरलिंक हटा पाएंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आप निम्नलिखित शर्तें पूरी करते हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है।
- विजुअल स्टूडियो जैसा विकास वातावरण।

## चरण 1: HTML फ़ाइल लोड करना और हाइपरलिंक हटाना
इस चरण में, हम HTML फ़ाइल लोड करेंगे और परिणामी पीडीएफ दस्तावेज़ से हाइपरलिंक हटा देंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// HTML लोडिंग विकल्पों का उपयोग करके HTML फ़ाइल लोड करें
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// दस्तावेज़ के पहले पृष्ठ की टिप्पणियाँ ब्राउज़ करें
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // जांचें कि क्या एनोटेशन एक लिंक है
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // जांचें कि क्या कार्रवाई GoToURIAction प्रकार की है
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // मेल खाने वाले पाठ अंशों को खोजने के लिए पाठ खंड अवशोषक का उपयोग करें
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // मेल खाने वाले टेक्स्ट अंशों के माध्यम से लूप करें और हाइपरलिंक्स से विशेषताएँ हटा दें
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // पृष्ठ से एनोटेशन हटाएँ
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` उस वास्तविक निर्देशिका के साथ जहां आपकी HTML फ़ाइल स्थित है।

## चरण 2: परिणामी पीडीएफ फाइल को सहेजना
अंत में, हम परिणामी पीडीएफ फाइल को हाइपरलिंक के बिना सहेजेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// परिणामी पीडीएफ फाइल को सेव करें
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 उपरोक्त कोड परिणामी पीडीएफ फाइल को फ़ाइल नाम के साथ सहेजता है`"RemoveHyperlinksFromText_out.pdf"`.

### .NET के लिए Aspose.PDF का उपयोग करके HTML से कनवर्ट करने के बाद हाइपरलिंक हटाने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.PDF का उपयोग करके HTML फ़ाइल से उत्पन्न पीडीएफ फ़ाइल से हाइपरलिंक हटाने की चरण-दर-चरण प्रक्रिया को कवर किया है। ऊपर वर्णित निर्देशों का पालन करके, आप परिणामी पीडीएफ फ़ाइल से हाइपरलिंक को सफलतापूर्वक हटाने में सक्षम होंगे।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उ: .NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को C# अनुप्रयोगों में PDF दस्तावेज़ों के साथ काम करने में सक्षम बनाती है। यह कार्यात्मकताओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें HTML फ़ाइलों को पीडीएफ में परिवर्तित करने और पीडीएफ सामग्री में हेरफेर करने की क्षमता शामिल है।

#### प्रश्न: मैं पीडीएफ फाइल से हाइपरलिंक क्यों हटाना चाहूंगा?

उ: पीडीएफ फाइल से हाइपरलिंक हटाने के कई कारण हैं। उदाहरण के लिए, हो सकता है कि आप मुद्रण या संग्रह उद्देश्यों के लिए बाहरी लिंक को हटाना चाहें या यह सुनिश्चित करना चाहें कि पीडीएफ सामग्री हाइपरलिंक के माध्यम से नेविगेट करने योग्य नहीं है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके HTML फ़ाइल कैसे लोड कर सकता हूं और हाइपरलिंक कैसे हटा सकता हूं?

 उ: HTML फ़ाइल लोड करने और हाइपरलिंक हटाने के लिए, आप .NET के लिए Aspose.PDF का उपयोग कर सकते हैं`HtmlLoadOptions` कक्षा। लिंक एनोटेशन ढूंढने और उनकी विशेषताओं को संशोधित करने के लिए पीडीएफ पृष्ठों के एनोटेशन के माध्यम से दोहराएं।

#### प्रश्न: क्या मैं परिणामी पीडीएफ के लिए आउटपुट फ़ाइल नाम को अनुकूलित कर सकता हूं?

उ: हाँ, आप पीडीएफ दस्तावेज़ को सहेजने वाले कोड को संशोधित करके परिणामी पीडीएफ फ़ाइल के लिए आउटपुट फ़ाइल नाम को अनुकूलित कर सकते हैं। बस वांछित फ़ाइल नाम बदलें`doc.Save()` तरीका।

#### प्रश्न: क्या कुछ मानदंडों के आधार पर हाइपरलिंक को चुनिंदा रूप से हटाना संभव है?

उत्तर: हां, आप विशिष्ट मानदंडों के आधार पर हाइपरलिंक को चुनिंदा रूप से हटा सकते हैं। उदाहरण के लिए, आप केवल बाहरी लिंक या विशिष्ट यूआरएल की ओर इशारा करने वाले लिंक को हटाना चुन सकते हैं।