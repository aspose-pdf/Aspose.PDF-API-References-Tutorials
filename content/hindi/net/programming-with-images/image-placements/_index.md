---
title: छवि प्लेसमेंट
linktitle: छवि प्लेसमेंट
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: PDF दस्तावेज़ में चित्र रखने के लिए .NET के लिए Aspose.PDF का उपयोग करना सीखें।
type: docs
weight: 170
url: /hi/net/programming-with-images/image-placements/
---
इस ट्यूटोरियल में, हम PDF दस्तावेज़ों के साथ काम करने और छवियों पर ऑपरेशन करने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करेंगे। हम एक PDF दस्तावेज़ लोड करेंगे, छवि प्लेसमेंट जानकारी निकालेंगे, और छवियों को उनके दृश्यमान आयामों के साथ पुनः प्राप्त करेंगे।

## चरण 1: वातावरण की स्थापना
आरंभ करने से पहले, सुनिश्चित करें कि आपने अपना विकास परिवेश निम्नलिखित के साथ सेट कर लिया है:
- आपकी मशीन पर .NET के लिए Aspose.PDF स्थापित है।
- AC# परियोजना उपयोग के लिए तैयार है।

## चरण 2: पीडीएफ दस्तावेज़ लोड करना
शुरू करने के लिए, हमें उस PDF दस्तावेज़ को लोड करना होगा जिसे हम प्रोसेस करना चाहते हैं। सुनिश्चित करें कि आपके पास PDF दस्तावेज़ वाली निर्देशिका का सही पथ है।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// स्रोत PDF दस्तावेज़ लोड करें
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` पीडीएफ फाइल युक्त आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 3: छवियों से प्लेसमेंट जानकारी निकालें
 अब जबकि हमने PDF दस्तावेज़ लोड कर लिया है, हम छवियों से प्लेसमेंट जानकारी निकाल सकते हैं। हम उपयोग करेंगे`ImagePlacementAbsorber`दस्तावेज़ के पहले पृष्ठ से छवि स्थानों को अवशोषित करने के लिए।

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// पहले पृष्ठ की सामग्री लोड करें
doc.Pages[1].Accept(abs);
```

हमने अब दस्तावेज़ के पहले पृष्ठ से छवि प्लेसमेंट जानकारी निकाल ली है।

## चरण 4: दृश्यमान आयामों वाली छवियां प्राप्त करना
अब हम पहले निकाली गई प्लेसमेंट जानकारी से उनके दृश्यमान आयामों के साथ चित्र प्राप्त करेंगे।

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // छवि गुण प्राप्त करें
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // दृश्यमान आयामों के साथ छवि पुनः प्राप्त करें
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // संसाधनों से छवि प्राप्त करें
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // वास्तविक आयामों के साथ एक छवि बनाएँ
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

इस लूप में, हम प्रत्येक छवि के गुणों को पुनः प्राप्त करते हैं, जैसे कि चौड़ाई, ऊँचाई, निचले बाएँ कोने के X और Y निर्देशांक, और क्षैतिज और ऊर्ध्वाधर रिज़ॉल्यूशन। फिर हम प्लेसमेंट जानकारी का उपयोग करके प्रत्येक छवि को उसके दृश्यमान आयामों के साथ पुनः प्राप्त करते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके छवि प्लेसमेंट के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// स्रोत PDF दस्तावेज़ लोड करें
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// प्रथम पृष्ठ की सामग्री लोड करें
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// छवि गुण प्राप्त करें
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// दृश्यमान आयामों के साथ छवि पुनर्प्राप्त करें
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// संसाधनों से छवि पुनर्प्राप्त करें
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//वास्तविक आयामों के साथ बिटमैप बनाएं
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## निष्कर्ष
बधाई हो! अब आप सीख चुके हैं कि PDF दस्तावेज़ में छवि प्लेसमेंट करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। हमने प्रदान किए गए C# स्रोत कोड को समझाया, जो आपको PDF दस्तावेज़ लोड करने, छवियों से प्लेसमेंट जानकारी निकालने और दृश्यमान आयामों के साथ छवियों को पुनः प्राप्त करने की अनुमति देता है। Aspose.PDF के साथ और अधिक प्रयोग करने के लिए स्वतंत्र महसूस करें और इसकी कई अन्य विशेषताओं का पता लगाएं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से छवि प्लेसमेंट जानकारी निकालने का उद्देश्य क्या है?

उत्तर: छवि प्लेसमेंट जानकारी निकालने से आप PDF दस्तावेज़ में छवियों की स्थिति, आयाम और रिज़ॉल्यूशन को पुनः प्राप्त कर सकते हैं। यह जानकारी सटीक छवि हेरफेर और विश्लेषण के लिए आवश्यक है।

#### प्रश्न: .NET के लिए Aspose.PDF एक PDF दस्तावेज़ से छवि प्लेसमेंट जानकारी निकालने में कैसे मदद करता है?

 उत्तर: .NET के लिए Aspose.PDF प्रदान करता है`ImagePlacementAbsorber`क्लास, जिसका उपयोग पीडीएफ दस्तावेज़ से छवि प्लेसमेंट विवरण को अवशोषित करने के लिए किया जा सकता है। प्रदान किया गया कोड दर्शाता है कि छवि प्लेसमेंट जानकारी प्राप्त करने के लिए इस क्लास का उपयोग कैसे किया जाए।

#### प्रश्न: वास्तविक दुनिया के परिदृश्यों में छवि प्लेसमेंट जानकारी का उपयोग किस लिए किया जा सकता है?

उत्तर: छवि प्लेसमेंट जानकारी ऐसे कार्यों के लिए मूल्यवान है जैसे कि सटीक छवि संरेखण सुनिश्चित करना, छवि आयामों की गणना करना, छवि गुणवत्ता की पुष्टि करना, और PDF दस्तावेज़ के भीतर छवि उपयोग पर रिपोर्ट तैयार करना।

#### प्रश्न: कोड नमूना छवि प्लेसमेंट जानकारी का सटीक निष्कर्षण कैसे सुनिश्चित करता है?

 उत्तर: कोड नमूना निम्नलिखित का उपयोग करता है`ImagePlacementAbsorber` क्लास का उपयोग किसी निर्दिष्ट पृष्ठ की सामग्री को पार करने, छवि प्लेसमेंट की पहचान करने और उनकी विशेषताओं को पुनः प्राप्त करने के लिए किया जाता है, जैसे कि चौड़ाई, ऊंचाई, निर्देशांक और रिज़ॉल्यूशन।

#### प्रश्न: क्या कोड को एकाधिक पृष्ठों या दस्तावेजों में छवियों को संसाधित करने के लिए विस्तारित किया जा सकता है?

उत्तर: हां, छवि प्लेसमेंट जानकारी निकालने और छवि से संबंधित कार्य करने के लिए कोड को कई पृष्ठों या दस्तावेजों के माध्यम से पुनरावृत्त करके विस्तारित किया जा सकता है।

#### प्रश्न: कोड प्लेसमेंट जानकारी के आधार पर छवियों को उनके दृश्यमान आयामों के साथ कैसे प्राप्त करता है?

उत्तर: कोड नमूना संसाधनों से छवि डेटा निकालता है, वास्तविक आयामों के साथ एक बिटमैप छवि बनाता है, और चौड़ाई, ऊंचाई, निर्देशांक और रिज़ॉल्यूशन जैसे गुण प्रदान करता है।

#### प्रश्न: क्या यह दृष्टिकोण अनेक छवियों वाले बड़े PDF दस्तावेज़ों के लिए प्रभावी है?

उत्तर: हां, .NET के लिए Aspose.PDF प्रदर्शन और संसाधन उपयोग के लिए अनुकूलित है। यह बड़े PDF दस्तावेज़ों से भी छवि प्लेसमेंट जानकारी को कुशलतापूर्वक निकालता है।

#### प्रश्न: छवि प्लेसमेंट जानकारी को समझने और उसका उपयोग करने से डेवलपर्स को क्या लाभ हो सकता है?

उत्तर: डेवलपर्स पीडीएफ दस्तावेजों में सटीक छवि हेरफेर, संरेखण और विश्लेषण सुनिश्चित कर सकते हैं। यह जानकारी उन्हें छवि प्रसंस्करण, रिपोर्टिंग और गुणवत्ता आश्वासन के लिए अनुप्रयोग बनाने में सक्षम बनाती है।

#### प्रश्न: क्या कोड को अतिरिक्त छवि-संबंधी विशेषताओं या मेटाडेटा को निकालने के लिए अनुकूलित किया जा सकता है?

उत्तर: बिल्कुल, कोड को अतिरिक्त विशेषताओं को निकालने के लिए बढ़ाया जा सकता है, जैसे छवि प्रकार, रंग स्थान, संपीड़न, और अधिक, .NET के लिए Aspose.PDF द्वारा प्रदान की गई उपयुक्त कक्षाओं और विधियों का उपयोग करके।

#### प्रश्न: इस ट्यूटोरियल में दिए गए निष्कर्ष का क्या महत्व है?

उत्तर: निष्कर्ष ट्यूटोरियल की सामग्री को सारांशित करता है और छवि प्लेसमेंट से परे अपनी क्षमताओं का लाभ उठाने के लिए .NET के लिए Aspose.PDF की आगे की खोज को प्रोत्साहित करता है, जिससे विभिन्न PDF-संबंधित कार्यों के लिए दरवाजे खुलते हैं।