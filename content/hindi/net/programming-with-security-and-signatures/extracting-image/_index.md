---
title: छवि निकालना
linktitle: छवि निकालना
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ आसानी से PDF दस्तावेज़ों से छवियां निकालें।
type: docs
weight: 70
url: /hi/net/programming-with-security-and-signatures/extracting-image/
---
पीडीएफ दस्तावेज़ से छवियां निकालना कई मामलों में उपयोगी हो सकता है। .NET के लिए Aspose.PDF के साथ, आप निम्नलिखित स्रोत कोड का उपयोग करके आसानी से छवियां निकाल सकते हैं:

## चरण 1: आवश्यक पुस्तकालय आयात करें

शुरू करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करनी होगी। यहां आवश्यक आयात निर्देश दिए गए हैं:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## चरण 2: दस्तावेज़ फ़ोल्डर में पथ सेट करें

 इस चरण में, आपको उस पीडीएफ फ़ाइल वाले फ़ोल्डर का पथ निर्दिष्ट करना होगा जिससे आप छवि निकालना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"`आपके दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## चरण 3: पीडीएफ दस्तावेज़ से छवि निकालें

अब हम निम्नलिखित कोड का उपयोग करके पीडीएफ दस्तावेज़ से छवि निकालेंगे:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

इस उदाहरण में, हम पीडीएफ दस्तावेज़ में फॉर्म के प्रत्येक फ़ील्ड को लूप करते हैं। यदि कोई हस्ताक्षर फ़ील्ड मिलती है, तो हम संबंधित छवि को निकालते हैं और उसे JPEG फ़ाइल में सहेजते हैं।

### .NET के लिए Aspose.PDF का उपयोग करके छवि निकालने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## निष्कर्ष

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से छवियां निकालने के लिए चरण-दर-चरण मार्गदर्शिका है। आप छवियां निकालने और आवश्यकतानुसार उनका उपयोग करने के लिए इस कोड को अपनी परियोजनाओं में एकीकृत कर सकते हैं।

उन्नत छवि निष्कर्षण और पीडीएफ दस्तावेज़ हेरफेर सुविधाओं पर अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ को अवश्य देखें।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या .NET के लिए Aspose.PDF शुरुआती लोगों के लिए उपयुक्त है?

उ: जबकि सी# प्रोग्रामिंग के साथ कुछ परिचितता सहायक है, हमारा ट्यूटोरियल शुरुआती-अनुकूल बनाया गया है, जो प्रत्येक चरण में आपका मार्गदर्शन करता है।

#### प्रश्न: क्या मैं एक साथ अनेक छवियाँ निकाल सकता हूँ?

उत्तर: बिल्कुल! लूप्स को लागू करके और दिए गए कोड को अपनाकर, आप एक ही पीडीएफ दस्तावेज़ से कई छवियां निकाल सकते हैं।

#### प्रश्न: क्या .NET के लिए Aspose.PDF छवि निष्कर्षण का एकमात्र समाधान है?

उ: जबकि अन्य उपकरण उपलब्ध हैं, .NET के लिए Aspose.PDF अपनी दक्षता और व्यापक सुविधाओं के लिए प्रसिद्ध है।

#### प्रश्न: क्या मैं निकाली गई छवियों का उपयोग व्यावसायिक उद्देश्यों के लिए कर सकता हूँ?

उत्तर: हां, एक बार निकाले जाने के बाद, छवियां व्यावसायिक परियोजनाओं सहित आवश्यकतानुसार उपयोग करने के लिए आपकी हैं।

#### प्रश्न: मुझे Aspose.PDF के साथ पीडीएफ हेरफेर पर अधिक संसाधन कहां मिल सकते हैं?

उत्तर: .NET के लिए Aspose.PDF के साथ उन्नत पीडीएफ हेरफेर पर ढेर सारे संसाधनों और अंतर्दृष्टि के लिए हमारे आधिकारिक दस्तावेज़ पर जाएँ।