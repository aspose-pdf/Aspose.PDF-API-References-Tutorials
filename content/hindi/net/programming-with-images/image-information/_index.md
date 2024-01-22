---
title: छवि जानकारी पीडीएफ फाइल में
linktitle: छवि जानकारी पीडीएफ फाइल में
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में छवि जानकारी निकालें।
type: docs
weight: 160
url: /hi/net/programming-with-images/image-information/
---
यह मार्गदर्शिका आपको चरण दर चरण बताएगी कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छवियों के बारे में जानकारी कैसे निकाली जाए। सुनिश्चित करें कि आपने अपना परिवेश पहले ही सेट कर लिया है और नीचे दिए गए चरणों का पालन करें:

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें

 सही दस्तावेज़ निर्देशिका सेट करना सुनिश्चित करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` कोड में उस निर्देशिका के पथ के साथ जहां आपका पीडीएफ दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत पीडीएफ फ़ाइल लोड करें

 इस चरण में, हम इसका उपयोग करके स्रोत पीडीएफ फाइल को लोड करेंगे`Document` Aspose.PDF की कक्षा। उपयोग`Document` कंस्ट्रक्टर और पीडीएफ दस्तावेज़ के लिए पथ पास करें।

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## चरण 3: डिफ़ॉल्ट रिज़ॉल्यूशन सेट करें

इस चरण में, हम छवियों के लिए डिफ़ॉल्ट रिज़ॉल्यूशन सेट करेंगे। उदाहरण में, डिफ़ॉल्ट रिज़ॉल्यूशन 72 पर सेट है।

```csharp
int defaultResolution = 72;
```

## चरण 4: ऑब्जेक्ट और काउंटर प्रारंभ करें

इस चरण में, हम छवि जानकारी प्राप्त करने के लिए आवश्यक वस्तुओं और काउंटरों को प्रारंभ करेंगे।

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## चरण 5: दस्तावेज़ के पहले पृष्ठ पर ऑपरेटरों के माध्यम से चक्र

इस चरण में, हम छवि-संबंधित संचालन की पहचान करने के लिए दस्तावेज़ के पहले पृष्ठ पर ऑपरेटरों के माध्यम से चलेंगे।

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## चरण 6: ऑपरेटरों को प्रबंधित करें और छवि जानकारी निकालें

इस चरण में, हम विभिन्न प्रकार के ऑपरेटरों को प्रबंधित करेंगे और छवियों के बारे में जानकारी निकालेंगे।

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//परिवर्तनों के लिए GSave और GRestore संचालन संभालें
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// परिवर्तनों के लिए कॉन्टेनेटमैट्रिक्स ऑपरेशन को संभालें
else if (opCtm != null)
{
     // परिवर्तन मैट्रिक्स लागू करें
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// छवियों के लिए Do ऑपरेशन को संभालें
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // छवि पुनः प्राप्त करें
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // छवि के आयाम पुनः प्राप्त करें
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // उपरोक्त जानकारी के आधार पर रिज़ॉल्यूशन की गणना करें
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // छवि जानकारी प्रदर्शित करें
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### .NET के लिए Aspose.PDF का उपयोग करके छवि जानकारी के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// स्रोत पीडीएफ फाइल लोड करें
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// छवि के लिए डिफ़ॉल्ट रिज़ॉल्यूशन परिभाषित करें
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// सरणी सूची ऑब्जेक्ट को परिभाषित करें जिसमें छवि नाम होंगे
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// स्टैक करने के लिए कोई ऑब्जेक्ट डालें
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// दस्तावेज़ के पहले पृष्ठ पर सभी ऑपरेटरों को प्राप्त करें
foreach (Operator op in doc.Pages[1].Contents)
{
	// परिवर्तनों को पहले सेट पर वापस लाने के लिए GSave/GRestore ऑपरेटरों का उपयोग करें
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// कॉन्टेनेटमैट्रिक्स ऑब्जेक्ट को इंस्टेंटियेट करें क्योंकि यह वर्तमान परिवर्तन मैट्रिक्स को परिभाषित करता है।
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Do ऑपरेटर बनाएं जो संसाधनों से ऑब्जेक्ट खींचता है। यह फॉर्म ऑब्जेक्ट और इमेज ऑब्जेक्ट खींचता है
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//पिछली स्थिति को सहेजें और वर्तमान स्थिति को स्टैक के शीर्ष पर धकेलें
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// वर्तमान स्थिति को हटा दें और पिछली स्थिति को पुनर्स्थापित करें
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// वर्तमान मैट्रिक्स को राज्य मैट्रिक्स से गुणा करें
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// यदि यह एक छवि आरेखण ऑपरेटर है
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// पहले पीडीएफ पेज की छवियों को रखने के लिए XImage ऑब्जेक्ट बनाएं
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// छवि आयाम प्राप्त करें
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// छवि की ऊंचाई और चौड़ाई की जानकारी प्राप्त करें
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// उपरोक्त जानकारी के आधार पर संकल्प की गणना करें
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// प्रत्येक छवि के आयाम और रिज़ॉल्यूशन की जानकारी प्रदर्शित करें
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## निष्कर्ष

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में छवि जानकारी कैसे निकाली जाती है। आप इस जानकारी का उपयोग अपने अनुप्रयोगों में विभिन्न छवि प्रसंस्करण कार्यों के लिए कर सकते हैं।

### पीडीएफ फ़ाइल में छवि जानकारी के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ से छवि जानकारी निकालने का उद्देश्य क्या है?

उ: पीडीएफ दस्तावेज़ से छवि जानकारी निकालने से दस्तावेज़ के भीतर छवियों के आयाम, रिज़ॉल्यूशन और अन्य विशेषताओं की जानकारी मिलती है। इस जानकारी का उपयोग छवि प्रसंस्करण, विश्लेषण या अनुकूलन कार्यों के लिए किया जा सकता है।

#### प्रश्न: .NET के लिए Aspose.PDF किसी PDF दस्तावेज़ से छवि जानकारी निकालने में कैसे सहायता करता है?

उ: .NET के लिए Aspose.PDF किसी PDF दस्तावेज़ की छवियों सहित उसकी सामग्री तक पहुंचने और उसका विश्लेषण करने के लिए उपकरण प्रदान करता है। प्रदान किया गया कोड दर्शाता है कि विभिन्न ऑपरेटरों का उपयोग करके छवि जानकारी कैसे निकालें और प्रदर्शित करें।

#### प्रश्न: इस पद्धति का उपयोग करके किस प्रकार की छवि जानकारी निकाली जा सकती है?

उ: यह विधि आपको पीडीएफ दस्तावेज़ के भीतर छवियों के लिए स्केल किए गए आयाम, रिज़ॉल्यूशन और छवि नाम जैसी जानकारी निकालने और प्रदर्शित करने की अनुमति देती है।

#### प्रश्न: कोड पीडीएफ दस्तावेज़ के भीतर छवि-संबंधित ऑपरेटरों की पहचान और प्रक्रिया कैसे करता है?

उ: कोड पीडीएफ दस्तावेज़ के एक निर्दिष्ट पृष्ठ पर ऑपरेटरों के माध्यम से दोहराया जाता है। यह छवि संचालन, परिवर्तन और प्रतिपादन से संबंधित ऑपरेटरों की पहचान और प्रक्रिया करता है।

#### प्रश्न: डिफ़ॉल्ट रिज़ॉल्यूशन का क्या महत्व है, और इसका उपयोग कोड में कैसे किया जाता है?

उ: छवियों के वास्तविक रिज़ॉल्यूशन की गणना करने के लिए डिफ़ॉल्ट रिज़ॉल्यूशन का उपयोग संदर्भ बिंदु के रूप में किया जाता है। कोड प्रत्येक छवि के रिज़ॉल्यूशन की गणना उसके आयामों और डिफ़ॉल्ट रिज़ॉल्यूशन सेटिंग के आधार पर करता है।

#### प्रश्न: निकाली गई छवि जानकारी का उपयोग वास्तविक दुनिया के परिदृश्यों में कैसे किया जा सकता है?

उ: निकाली गई छवि जानकारी का उपयोग छवि गुणवत्ता मूल्यांकन, छवि अनुकूलन, छवि थंबनेल बनाने और छवि-संबंधित निर्णय लेने की प्रक्रियाओं को सुविधाजनक बनाने जैसे कार्यों के लिए किया जा सकता है।

#### प्रश्न: क्या मैं अतिरिक्त छवि-संबंधित विशेषताओं को निकालने के लिए कोड को संशोधित कर सकता हूं?

उ: हां, आप छवियों की अतिरिक्त विशेषताओं, जैसे रंग स्थान, पिक्सेल गहराई, या छवि प्रकार निकालने के लिए कोड को अनुकूलित कर सकते हैं।

#### प्रश्न: क्या छवि जानकारी निष्कर्षण प्रक्रिया संसाधन-गहन या समय लेने वाली है?

उत्तर: छवि जानकारी निष्कर्षण प्रक्रिया कुशल और प्रदर्शन के लिए अनुकूलित है, जो संसाधन उपयोग और प्रसंस्करण समय पर न्यूनतम प्रभाव सुनिश्चित करती है।

#### प्रश्न: पीडीएफ दस्तावेज़ों से छवि जानकारी को पहचानने और निकालने से डेवलपर्स को कैसे लाभ हो सकता है?

उ: डेवलपर्स पीडीएफ दस्तावेज़ों के भीतर छवियों की विशेषताओं के बारे में जानकारी प्राप्त कर सकते हैं, जिससे वे छवि हेरफेर, प्रसंस्करण और अनुकूलन के संबंध में सूचित निर्णय लेने में सक्षम हो सकते हैं।

#### प्रश्न: क्या इस विधि का उपयोग छवियों वाले पीडीएफ दस्तावेज़ों के बैच प्रोसेसिंग के लिए किया जा सकता है?

उत्तर: हाँ, इस पद्धति को कई पृष्ठों या दस्तावेज़ों के माध्यम से पुनरावृत्त करके, छवि जानकारी निकालकर और छवि-संबंधी कार्यों को निष्पादित करके बैच प्रसंस्करण के लिए बढ़ाया जा सकता है।