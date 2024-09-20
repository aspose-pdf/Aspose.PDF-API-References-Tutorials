---
title: पीडीएफ फाइल में अक्षर हाइलाइट करें
linktitle: पीडीएफ फाइल में अक्षर हाइलाइट करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: इस व्यापक चरण-दर-चरण मार्गदर्शिका में .NET के लिए Aspose.PDF का उपयोग करके PDF में वर्णों को हाइलाइट करना सीखें।
type: docs
weight: 240
url: /hi/net/programming-with-text/highlight-character-in-pdf/
---
## परिचय

जब PDF के साथ काम करने की बात आती है, तो अक्सर टेक्स्ट या अक्षरों को हाइलाइट करने की ज़रूरत पड़ती है - चाहे अकादमिक उद्देश्यों के लिए, संपादन के लिए, या सिर्फ़ पठनीयता में सुधार के लिए। कल्पना करें कि आपके पास एक सुंदर दस्तावेज़ है, लेकिन आप कुछ हिस्सों पर ज़ोर देना चाहते हैं। यहीं पर हाइलाइटिंग की बात आती है! इस ट्यूटोरियल में, हम शक्तिशाली Aspose.PDF for .NET लाइब्रेरी का उपयोग करके PDF फ़ाइल में अक्षरों को हाइलाइट करने के तरीके के बारे में जानेंगे। 

## आवश्यक शर्तें

कोड में जाने से पहले, आइए सुनिश्चित करें कि हमारे पास वह सब कुछ है जिसकी हमें ज़रूरत है। आपको इसकी ज़रूरत होगी:

1. विकास परिवेश: यह ट्यूटोरियल मानता है कि आप विजुअल स्टूडियो या किसी समान .NET IDE में काम कर रहे हैं।
2.  .NET लाइब्रेरी के लिए Aspose.PDF: यदि आपने पहले से ऐसा नहीं किया है, तो आप कर सकते हैं[यहाँ पर डाउनलोड करो](https://releases.aspose.com/pdf/net/) और इसे अपने प्रोजेक्ट में जोड़ें. 
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग की प्रारंभिक जानकारी आपको कार्यान्वयन को आसानी से समझने में मदद करेगी।
4. एक पीडीएफ दस्तावेज़: आपके पास काम करने के लिए एक नमूना पीडीएफ फ़ाइल तैयार होनी चाहिए। आप एक बना सकते हैं या किसी मौजूदा दस्तावेज़ का उपयोग कर सकते हैं।

## पैकेज आयात करना

आरंभ करने के लिए, हमें आवश्यक नामस्थानों को आयात करना होगा। ऐसा करने के लिए, आपको उन्हें अपनी C# फ़ाइल के शीर्ष पर शामिल करना होगा:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

ये पैकेज एस्पोज लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेजों को बनाने, हेरफेर करने और प्रसंस्करण के लिए आवश्यक हैं।

अब, आइए आपकी पीडीएफ में अक्षरों को हाइलाइट करने के लिए प्रक्रिया को सरल चरणों में विभाजित करें। 

## चरण 1: पीडीएफ दस्तावेज़ को आरंभ करें

पहला कदम अपने PDF दस्तावेज़ को आरंभ करना है। इसमें उस PDF फ़ाइल को लोड करना शामिल है जिसके साथ आप काम करेंगे। इसे करने का तरीका यहां बताया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // सही रास्ता तय करना सुनिश्चित करें.
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
इस स्निपेट में, प्रतिस्थापित करें`YOUR DOCUMENT DIRECTORY` आपकी मशीन पर वास्तविक पथ के साथ जहाँ आपकी इनपुट पीडीएफ फाइल स्थित है।`Aspose.Pdf.Document` क्लास को आपके पीडीएफ को लोड करने के लिए इंस्टैंशिएट किया गया है।

## चरण 2: रेंडरिंग प्रक्रिया सेट करें

इसके बाद, हमें अपने दस्तावेज़ के लिए रेंडरिंग प्रक्रिया तैयार करनी होगी। यह पृष्ठ पर वर्णों को सटीक रूप से हाइलाइट करने के लिए आवश्यक है।

```csharp
int resolution = 150; // छवि कैप्चरिंग के लिए रिज़ॉल्यूशन सेट करें.
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
 हम स्पष्टता के लिए एक रिज़ॉल्यूशन परिभाषित करते हैं, जिससे पाठ को ठीक से प्रस्तुत किया जा सके।`PdfConverter`पीडीएफ पृष्ठों को चित्रों में बदल देता है ताकि हम उन पर चित्र बना सकें।

## चरण 3: ड्राइंग के लिए ग्राफ़िक्स ऑब्जेक्ट बनाएँ

ड्राइंग प्रक्रिया को सेट करने के बाद, हमें एक ग्राफ़िक्स ऑब्जेक्ट बनाना होगा जिसमें हम हाइलाइटिंग करेंगे:

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; // पैमाने का कारक।
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
यहाँ, हम बिटमैप इमेज से ग्राफ़िक्स ऑब्जेक्ट बनाते हैं। रूपांतरण आवश्यक रिज़ॉल्यूशन से सही ढंग से मेल खाने के लिए रेंडरिंग को समायोजित करने में मदद करता है।

## चरण 4: प्रत्येक पृष्ठ पर जाएँ और टेक्स्ट हाइलाइट करें

अब, आइए पीडीएफ के प्रत्येक पृष्ठ पर जाएं और उन पाठ अंशों को ढूंढें जिन्हें हम हाइलाइट करना चाहते हैं:

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // Aspose में पृष्ठ 1-इंडेक्स किए गए हैं।
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
 हम प्रत्येक पृष्ठ पर पहुंचते हैं और सभी पाठों को खोजते हैं`TextFragmentAbsorber` . नियमित अभिव्यक्ति पैटर्न`@"[\S]+"` सभी गैर-रिक्त स्थान वर्णों को कैप्चर करता है.

## चरण 5: टेक्स्ट के टुकड़े निकालें और हाइलाइट करें

अब समय है टेक्स्ट के टुकड़ों को निकालने और उन्हें हाइलाइट करने का। इस प्रक्रिया में उन अक्षरों के चारों ओर आयत बनाना शामिल है जिन्हें हम हाइलाइट करना चाहते हैं:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    // यहाँ तर्क पर प्रकाश डाला गया है
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
हम प्रत्येक पाठ खंड, उसके खंडों और व्यक्तिगत वर्णों के माध्यम से लूप बनाते हैं, तथा पहले से निर्मित ग्राफिक्स ऑब्जेक्ट का उपयोग करके उनके चारों ओर आयताकार आकृतियाँ बनाते हैं।

## चरण 6: संशोधित छवि सहेजें

हाइलाइट करने के बाद, आपको परिणामी छवि को एक नई PNG फ़ाइल के रूप में सहेजना होगा:

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
यह पंक्ति आपके संशोधित बिटमैप चित्र को निर्दिष्ट निर्देशिका में PNG फ़ाइल के रूप में सहेजती है। 

## चरण 7: अपवाद प्रबंधन के साथ समापन

अंत में, अपने कोड को try-catch ब्लॉक में लपेटना अच्छा अभ्यास है, जिससे यह सुनिश्चित हो सके कि हम किसी भी अप्रत्याशित त्रुटि को सुचारू रूप से संभाल सकें:

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/)");
}
```

यह ब्लॉक प्रक्रिया के दौरान होने वाले किसी भी अपवाद को पकड़ लेता है और उपयोगकर्ता को सूचनात्मक फीडबैक देता है।

## निष्कर्ष

और अब आप इसे प्राप्त कर चुके हैं! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में सफलतापूर्वक वर्णों को हाइलाइट किया है। यह शक्तिशाली लाइब्रेरी PDF हेरफेर में अनंत संभावनाओं के द्वार खोलती है - चाहे आप एनोटेशन, फ़ॉर्म भरने या यहां तक कि दस्तावेज़ रूपांतरण के साथ काम कर रहे हों। Aspose के साथ अपनी यात्रा जारी रखते हुए, याद रखें कि अभ्यास महत्वपूर्ण है। विभिन्न सुविधाओं के साथ प्रयोग करते रहें, और आप जल्दी ही PDF प्रो बन जाएंगे!

## अक्सर पूछे जाने वाले प्रश्न

### .NET के लिए Aspose.PDF क्या है?
.NET के लिए Aspose.PDF एक लाइब्रेरी है जो .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से PDF दस्तावेज़ों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देता है।

### क्या मैं एक साथ कई पाठ अंशों को हाइलाइट कर सकता हूँ?
हां, प्रदान किए गए कोड को पीडीएफ के भीतर सभी पाठ के माध्यम से लूपिंग करके कई टुकड़ों को हाइलाइट करने के लिए अनुकूलित किया जा सकता है।

### क्या Aspose.PDF का कोई निःशुल्क संस्करण उपलब्ध है?
हां, Aspose एक निःशुल्क परीक्षण प्रदान करता है, इसलिए आप खरीदने से पहले लाइब्रेरी का परीक्षण कर सकते हैं।

### क्या मुझे Aspose.PDF का उपयोग करने के लिए किसी लाइसेंस की आवश्यकता है?
हां, व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता होती है, लेकिन आप परीक्षण के लिए 30-दिन का अस्थायी लाइसेंस प्राप्त कर सकते हैं।

### मुझे अधिक दस्तावेज कहां मिल सकते हैं?
 आप इसका संदर्भ ले सकते हैं[Aspose.PDF दस्तावेज़ीकरण](https://reference.aspose.com/pdf/net/) कार्यान्वयन और सुविधाओं पर अधिक विस्तृत जानकारी के लिए.